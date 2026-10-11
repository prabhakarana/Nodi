# Nodi — Instructions for Claude

Nodi: "Every moment has value." Guiding principle: **Awareness without guilt.**

## Required before significant work

Before any significant feature, architecture change, or copy/UX decision, read and follow, in order:

1. `PRODUCT_VISION.md` — the constitution; it overrides feature requests that conflict with it.
2. `docs/DECISIONS.md` — accepted decisions.
3. `docs/OPEN_QUESTIONS.md` — do not silently resolve these; surface them.
4. `docs/ASSUMPTIONS.md` — never present a hypothesis as fact.
5. `docs/ROADMAP.md` — stay within the current milestone.

## Rules

- Preserve the Intend → Observe → Account → Reflect → Adjust loop.
- Never shame, score, or moralize activities; no implication that rest is wasteful or that time has universal monetary value.
- Record provenance (observed / manual / inferred / corrected) on data; no hidden corrections or double-counting.
- Local-first, minimal collection; export and deletion must always work. Automatic tracking is optional and explainable.
- Do not build non-goals (see `PRODUCT_VISION.md` §6) without explicit approval recorded in `docs/DECISIONS.md`.
- Do not invent user research, competitor capabilities, or validation results. Do not claim uniqueness without evidence.
- If a request conflicts with the constitution, stop and say so rather than complying silently.
- Unresolved choices go in `docs/OPEN_QUESTIONS.md`; accepted ones in `docs/DECISIONS.md`.

## Workflow

- `main` is the stable baseline; use short-lived branches (e.g. `feat/...`). No permanent `develop` branch.
- Do not merge, push, or change repository settings without explicit authorization.
