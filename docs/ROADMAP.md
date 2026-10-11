# Nodi — Roadmap

Milestones are sequential. Do not start a milestone until the previous one's exit criteria are met or consciously waived in `docs/DECISIONS.md`. Scope is bounded by `PRODUCT_VISION.md`.

## M0 — Foundation (current)
Product constitution and supporting docs.
**Exit:** All seven foundation documents reviewed and accepted by the product owner; open questions needed for M1 triaged.

## M1 — Technical foundation
Choose and record stack, local-persistence approach, data model (including provenance), and tooling (lint, test, CI).
**Exit:** Stack and storage decisions recorded in `docs/DECISIONS.md`; empty responsive app shell runs on desktop and mobile viewports; checks pass.

## M2 — Core ledger
User-defined categories, manual entries, editing, local persistence.
**Exit:** A user can create categories, add/edit/delete entries, and data survives reload; provenance stored per entry; no double-counting rules defined and tested.

## M3 — Timers
Start, pause, resume, stop.
**Exit:** Timer produces ledger entries with correct durations across pause/resume and page reload; overlap handling with manual entries is defined and tested.

## M4 — Intend and account
Daily intentions and daily allocation summary (intended vs. actual, including unclassified time).
**Exit:** Summary reconciles with ledger totals; presentation is non-judgmental (copy reviewed against principle 3).

## M5 — Reflect and review
End-of-day reflection and weekly review.
**Exit:** Reflections persist and link to their day; weekly review helps a user decide something (supports Adjust), not just display charts.

## M6 — Data ownership and release readiness
Export, full deletion, accessibility and privacy review.
**Exit:** Export is complete and documented; deletion removes all local data; no network transmission of user data; accessibility pass completed.

## M7 — Validation with real users
Use the MVP with real users to test the differentiating hypothesis.
**Exit:** Evidence gathered and recorded in `docs/ASSUMPTIONS.md`; go / change / stop decision recorded in `docs/DECISIONS.md`. Criteria for "success" must first be defined (see OPEN_QUESTIONS).

## Later (not approved)
Optional browser extension for website/domain observation (opt-in, explainable, with its own privacy review). Anything in the non-goals list requires separate approval.

## Proposed amendment (not adopted): M0.5 — Pre-build validation
Per `docs/VALIDATION_PLAN.md`, a competitor verification pass and a 14-day diary experiment are recommended before M1. Pending the product owner's decision (OPEN_QUESTIONS #14, #16); until then the milestones above are unchanged.
