# Nodi Event Schema — Draft 0

**Status:** Proposal, not accepted. `schemaVersion` is `0` (unstable) until the owner accepts it; then it becomes `1` and changes need a `DECISIONS.md` entry and a migration rule.
**Implements:** D-007 (platform-neutral format). **Answers draft of:** OPEN_QUESTIONS #22.
**Files:** machine-readable schema `docs/schema/nodi-export.schema.json` (JSON Schema 2020-12); example `docs/schema/examples/export-basic.json`.

Labels: **Rule** = proposed normative requirement; **Rationale**; **Open** = needs an owner decision (listed in §9).

## 1. Goals and non-goals

Goals:
- One format shared by the throwaway web tool and future Apple/Android/Windows apps, usable for export, import, and backup.
- Supports principles 4 (provenance), 6 (export/deletion), and 7 (no double-counting, no hidden corrections, no invented classifications).
- Easy to implement in TypeScript and Swift (`Codable`): every variant has a `kind` discriminator; no polymorphism by field presence.

Non-goals: not a sync protocol (cross-device sync is a non-goal; no CRDT, tombstones, or merge semantics); not a raw-telemetry format; not a storage layout (each platform may store however it likes if it can round-trip this).

## 2. Concepts

| Concept | Meaning |
|---|---|
| **Entry** | A span of the user's time (one or more intervals) with a source, an optional category, and an optional intention link. The core record. |
| **Category** | User-defined label. No built-in "productive/unproductive" attribute, ever (principle 3). |
| **Intention** | What the user meant to do for a day or week; optionally category-linked, with an optional soft target. |
| **Reflection** | Free-text end-of-day or weekly note. No score or mood scale. |
| **Unaccounted time** | Time with **no entry** (derived, not stored). |
| **Unclassified time** | Time **with an entry** whose `categoryId` is `null`. |

Unaccounted and unclassified are deliberately different: one means "I don't know where it went", the other "I know what I did but haven't named it".

## 3. Envelope

`{ format: "nodi-export", schemaVersion, exportedAt, app{name, version, platform, installId?}, data{categories, intentions, entries, reflections} }`

- **Rule:** Importers accept unknown extra fields (ignore or preserve) and never reject a file only because a newer writer added fields. They do reject a higher major `schemaVersion` than they understand.
- `installId` is a random per-install UUID, never a hardware or account identifier (principle 6).

## 4. Entry

### 4.1 Time
- **Rule:** Instants are UTC RFC 3339 (`...Z`, ≤ millisecond precision). Each entry also carries `tz`, the IANA zone at the time, so the local day is derivable even after travel or DST changes. Local dates (`YYYY-MM-DD`) appear only where the user thinks in calendar days (intentions, reflections).
- **Rule:** `intervals` is a non-empty, sorted, non-overlapping list with `start < end`. Duration = sum of intervals. A paused-and-resumed timer yields one entry with several intervals; the gap is not counted.
- **Rule:** No interval may end in the future (clock-skew tolerance, e.g. 5 min; **Open**).
- An entry that crosses local midnight is stored once; day views split it by `tz` at read time. **Rationale:** storing views would create two records for one activity.
- **Open:** user-defined "day start" (e.g. 04:00) for late-night activity — affects only the read-time split, not storage.

### 4.2 Source (provenance)
`source.kind` is one of:

| kind | Meaning | Extra fields |
|---|---|---|
| `manual` | User typed it in after the fact | — |
| `timer` | User ran an in-app timer | — |
| `observed` | An optional observer recorded it | `observer{id,type,version?}`, `subject?{type: app\|domain\|none, identifier?, displayName?}`, `externalKey` |
| `inferred` | A user-visible rule proposed it | `method`, `basis[]` (entry ids), `explanation` (plain language) |

- **Rule:** `observed` subjects are the coarsest useful level: an app identifier or domain, never a full URL, page title, window title, or content. **Rationale:** privacy-first, minimal collection (principle 6). **Open:** whether even domain is acceptable by default.
- **Rule:** `externalKey` is unique per observer so re-importing the same observation is idempotent (no double-counting).
- **Rule:** `inferred` entries must say why and from what. Inferred entries are proposals the user can accept (the user then re-saves them as `manual`, with a correction note) or discard; they must never silently count as the user's own account (**Open**: whether they count before acceptance; default proposal: they do not).
- "Corrected" is **not** a source. See next.

### 4.3 Corrections (no hidden edits)
- **Rule:** Any user edit of an existing entry's meaningful fields (intervals, category, title, intention link) appends `{at, by:"user", fields:{name:{from,to}}, note?}` to `corrections`. The current value is the entry's current field; history is in `corrections`.
- **Rule:** Observer re-sync must not overwrite a corrected entry (the `externalKey` match is skipped or flagged).
- **Rule:** Displaying an entry shows its original source and a "corrected" marker when `corrections` is non-empty (derived; not stored as a separate flag).
- **Open:** whether to let the user purge correction history without deleting the entry. (Deleting the entry deletes its history.)

### 4.4 Category and intention link
- **Rule:** `categoryId` is **required** and may be `null` (unclassified). If non-null, `categoryAssignedBy` (`user` or `user_rule`) is required. There is no machine-assigned category value; no classification is invented (principle 7).
- **Rule:** `user_rule` means a rule the user created and can see (e.g. "domain X → Reading"). **Open:** whether rules ship in v1.
- **Rule:** `intentionId` is set only by the user, never inferred. Comparison against intentions is otherwise by category.

## 5. Intention and Reflection
- Intention: `scope` (`day`|`week`), `date` (the day or the user's week start), `text` (≤ 280), optional `categoryId`, optional `target{minutes, comparison: about|at_least|at_most}`. **Open:** `at_most` can read as a cap/limit; confirm it fits principle 3 or drop it for the MVP.
- Reflection: `scope`, `date`, free `text` (≤ 5000). **Open:** any structured prompt answers, mood scale (default: none).

## 6. Deletion and export
- **Rule:** Deletion is physical: remove the record (and its `corrections`) from local storage. The format has no tombstones.
- **Rule:** "Delete everything" removes all four collections plus any local settings and `installId`.
- **Rule:** Export is complete (all four collections) and human-inspectable JSON. Importing the same file twice must not duplicate (ids and `externalKey`).

## 7. Account derivation (non-normative proposal; not part of the stored format)

The daily account is computed from entries, never stored:
1. Assign each interval to a local day via `tz`.
2. **Overlaps are allowed in storage** (timer plus manual entry, observer plus manual). The account counts any moment **once**, using this precedence proposal: user-authored (`manual`, `timer`, including corrected) > `observed` > `inferred`.
3. When two user-authored entries overlap, **do not auto-resolve**: show both, flag the conflict, let the user fix it. Observed spans covered by a user entry are shown as "covered", not deleted.
4. Unaccounted = day length (24 h by default, **Open** whether waking hours) − counted time. Unclassified = counted time with `categoryId == null`.
This resolves nothing silently, consistent with principle 7. Tracks OPEN_QUESTIONS #4 and #5.

## 8. Invariants the schema cannot express (to be tested)

1. Unique ids; every `categoryId`, `intentionId`, `basis[]` id resolves.
2. Intervals sorted, non-overlapping, `start < end`, not in the future.
3. `(observer.id, externalKey)` unique.
4. `tz` is a valid IANA name.
5. Round-trip: export → import → export is byte-stable after normalization.
6. A correction's `to` equals the entry's current field value at the time of the correction (checked on write).

Verification so far: the schema validates the example file and rejects eight deliberately broken variants (missing assignedBy, missing categoryId, empty intervals, non-UTC instant, unknown source kind, inferred without explanation, observed without externalKey, malformed id). No other testing has been done; this is a draft.

## 9. Decisions needed from the owner

See OPEN_QUESTIONS #27–#34. Highest impact: overlap precedence (#27), whether inferred entries count before acceptance (#28), and whether observed `domain` is acceptable by default (#29).
