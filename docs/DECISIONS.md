# Decisions

Accepted architectural and product decisions. Append new entries; do not rewrite history. If a decision is reversed, add a new entry that supersedes it.

Format: ID, date, status, decision, rationale.

## D-001 — Product identity
- **Date:** 2026-10-11
- **Status:** Accepted
- **Decision:** Product name Nodi; tagline "Every moment has value."; guiding principle "Awareness without guilt."
- **Rationale:** Approved by the product owner.

## D-002 — Product constitution
- **Date:** 2026-10-11
- **Status:** Accepted (pending review of the M0 branch)
- **Decision:** `PRODUCT_VISION.md` is the governing document; `CLAUDE.md` requires all work to follow it; significant work requires reviewing the docs in `CLAUDE.md` first.
- **Rationale:** Preserve strategic intent across sessions.

## D-003 — Initial platform and scope
- **Date:** 2026-10-11
- **Status:** Accepted
- **Decision:** Responsive web app for desktop and mobile; MVP scope as listed in `PRODUCT_VISION.md` §5. Browser-extension tracking is a later, optional phase.
- **Rationale:** Validate the simplest useful experience first (principle 8).

## D-004 — Non-goals
- **Date:** 2026-10-11
- **Status:** Accepted
- **Decision:** App blocking, leaderboards, public profiles, AI coaching, paid subscriptions, and cross-device cloud sync are out of scope unless separately approved here.

## D-005 — Git workflow
- **Date:** 2026-10-11
- **Status:** Accepted
- **Decision:** `main` is the stable baseline; short-lived feature branches (e.g. `feat/product-constitution`); no permanent `develop` branch; no merging or pushing without explicit authorization.

## D-006 — Platform strategy: Apple-first native long term; throwaway web validation tool now
- **Date:** 2026-10-11
- **Status:** Accepted by the product owner
- **Decision:**
  1. The long-term product is **native, Apple first** (iOS, iPadOS, macOS). Android and Windows are later, each with its own native code. No long-term dependence on a PWA or hybrid wrapper (Capacitor/Tauri/Electron are not the target path).
  2. **Now**, build only a small, **throwaway web tool** to validate the hypothesis (manual entries, timers, intentions, daily summary). It is disposable; no investment in making it the production app.
  3. Sequencing: competitor verification and the diary experiment (`docs/VALIDATION_PLAN.md`) come before any native build.
- **Rationale:** Automatic observation requires platform-native code; a web app cannot observe other apps or the device. Native is where the long-term product has to live. A web tool is the cheapest way to test the unproven core hypothesis first.
- **Not decided here:** native device-wide automatic tracking is **not** approved by this entry (see D-007 and OPEN_QUESTIONS #21). The shared-core language, the web tool's stack, and the Apple Screen Time feasibility are open.
- **Effect on earlier decisions:** Narrows D-003 ("responsive web app" as the initial platform): the web app is now a validation tool, not the shipped product. Sections of `PRODUCT_VISION.md` and `docs/ROADMAP.md` that assume a shipped web app are annotated to point here.

## D-007 — Platform-neutral observation event format is a requirement
- **Date:** 2026-10-11
- **Status:** Accepted by the product owner
- **Decision:** The ledger's data model is defined independently of any UI or platform. Every ledger entry is an event with at least: time range, source (manual / timer / observed / inferred), provenance including corrections, user-defined category, and an optional intention link. The throwaway web tool and any future native observer must write the same format. The format must be exportable and importable.
- **Rationale:** Preserves the validated learning and the user's data across the move from web tool to native apps; supports principles 4 (provenance) and 7 (honest accounting).
- **Not decided here:** the concrete schema (OPEN_QUESTIONS #22).

## D-008 — Native automatic tracking: scope not yet approved
- **Date:** 2026-10-11
- **Status:** Open — recorded so it is not assumed
- **Decision:** `PRODUCT_VISION.md` limits automatic tracking to a later, optional browser-extension phase. Native device-wide tracking goes beyond this and remains a non-approved scope until the owner approves it explicitly, after the Apple feasibility spike and a privacy review. Until then, no automatic-tracking work and no claim of device-wide observation.
