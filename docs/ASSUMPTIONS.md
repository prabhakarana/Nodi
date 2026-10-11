# Assumptions

Separates what is known from what is believed. Nothing moves to "Validated" without cited evidence. As of M0, **no user research, competitor analysis, or validation has been performed.**

## Validated facts

| Fact | Evidence |
|------|----------|
| The repository contained only a `LICENSE` file and one initial commit when this documentation was created. | Git history inspection, 2026-10-11 |
| The product owner has approved the name, tagline, guiding principle, MVP scope, and non-goals. | Product owner's Prompt 00 |
| The Prompt 01 competitor review (2026-10-11) had no direct access to any product or vendor page; direct fetches failed (DNS error / proxy 403). Findings come from search summaries only. | `docs/COMPETITIVE_ANALYSIS.md` §0 |
| As of 2026-10-11 **no competitor capability is Verified** in this repository; all are Unverified or Inferred. | `docs/COMPETITIVE_ANALYSIS.md` §3 |

## Hypotheses (unvalidated)

| # | Hypothesis | How it could be tested |
|---|-----------|------------------------|
| H1 | A unified personal time ledger (manual entries, timers, later permitted automatic observations) helps people reconcile actual time with intentions across digital and offline life. | Real-user MVP use (M7); criteria TBD |
| H2 | Many people who feel their time slips away are not productivity enthusiasts and want an approachable, non-judgmental tool. | User interviews / usage observation |
| H3 | The Intend → Observe → Account → Reflect → Adjust loop leads users to change how they allocate attention. | Longitudinal usage |
| H4 | A personal currency metaphor makes time more tangible without inducing guilt. | Copy/UX testing |
| H5 | Manual entries and timers alone provide enough value to justify the MVP before any automatic tracking. | MVP usage; retention of manual logging |
| H6 | Users value whole-life accounting (including rest and unclassified time) over work-only tracking. | Interviews; category usage |
| H7 | Intended-vs-actual comparison leads to more deliberate change than a plain time log. | 14-day diary experiment, conditions A/B (`docs/VALIDATION_PLAN.md` §3) |
| H8 | The "personal currency/ledger" vocabulary is understandable unaided and does not induce pressure or guilt; a plain wording may do as well or better. | Unaided comprehension test (`VALIDATION_PLAN.md` Q4) |
| H9 | Users will keep logging manually (entries and timers) long enough to benefit, without automatic tracking. | Adherence in the diary study |
| H10 | Per-entry provenance (observed / manual / inferred / corrected) matters to users and is not just overhead. | Diary study provenance marking; interviews |
| H11 | A narrow initial segment exists whose "time slips away" problem is specific enough to design for. Not yet chosen. | Recruitment screener results |

## Unverified claims about competitors

Search summaries of vendor pages (2026-10-11, not directly read, therefore **Unverified**) describe Ravelo as an iPhone app where useful-app and off-phone focus minutes are earned and spent to unlock apps, with default-locked distracting apps; Opal and Freedom as blocking/focus-session tools (Opal also with a daily Focus Score); RescueTime and ActivityWatch as automatic trackers (ActivityWatch open source with local storage); Toggl Track as a manual/timer tracker with goals. Whether any of them offers intentions, planned-vs-actual comparison, reflection, or provenance is **unknown**. See `docs/COMPETITIVE_ANALYSIS.md`.

Do not assert competitor capabilities, or their absence, in product copy or docs until verified by direct product access (OPEN_QUESTIONS #13).

## Inferences (reasoned, not observed)

- Competing on blocking or earn-to-unlock is off-constitution and a poor frame for Nodi.
- A web app cannot observe other apps or the phone; an extension can see only the browser. Most of life stays manual-entry.
- Financial vocabulary ("ledger", "spend", "currency") may carry scarcity or pressure connotations. To be tested, not assumed.

