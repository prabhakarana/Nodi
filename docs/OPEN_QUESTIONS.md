# Open Questions

Unresolved product and technical decisions. Do not resolve silently: when answered, move the outcome to `docs/DECISIONS.md` and mark the item resolved here.

| # | Question | Why it matters | Needed by |
|---|----------|----------------|-----------|
| 1 | What technology stack (framework, language) will the web app use? | Shapes everything after M1 | M1 |
| 2 | Which local persistence mechanism (e.g. IndexedDB, localStorage, other)? Storage limits and data-loss behavior on browser clear? | Local-first promise, export importance | M1 |
| 3 | What is the exact meaning of the "personal currency" metaphor (unit, budget per day, naming)? How do we avoid implying monetary value or scarcity guilt? | Core UX and principle 3 | M4 |
| 4 | How is time not accounted for represented ("unclassified")? Is a day 24h or waking hours? | Honest accounting | M2 |
| 5 | How are overlapping entries (manual vs. timer, concurrent timers) handled? | Avoid double-counting | M2–M3 |
| 6 | Can intentions be time-based, category-based, or both? Daily only, or recurring? | Intend step design | M4 |
| 7 | Should any narrower initial user segment be targeted for validation? | Validation design | M7 |
| 8 | What evidence would validate or invalidate the differentiating hypothesis (metrics, sample size, method)? | Prevents unfalsifiable claims | M7 |
| 9 | Is account/identity ever needed, or strictly anonymous local-only? | Privacy and sync non-goal | M1 |
| 10 | Browser-extension feasibility, permissions, and store policies for later phase? | Later optional phase | Post-MVP |
| 11 | Import of previously exported data in MVP? | Data ownership | M6 |
| 12 | Licensing/branding: confirm "Nodi" name availability and trademark checks. | Launch risk | Before public release |
| 13 | Competitor review: what do Ravelo and others actually offer today? (Not yet researched.) | Hypothesis honesty | Before positioning claims |
