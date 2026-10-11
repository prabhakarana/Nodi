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
