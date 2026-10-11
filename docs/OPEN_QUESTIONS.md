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
| 13 | Competitor verification: re-run `docs/COMPETITIVE_ANALYSIS.md` §5 with direct product access (Ravelo, Opal, Freedom, RescueTime, Toggl, ActivityWatch, Apple Screen Time, Digital Wellbeing, timeboxing tools). First pass was search-summary only. | Hypothesis honesty | Before positioning claims and before M1 data model |
| 14 | Approve, edit, or reject the proposed 14-day diary experiment, its pass/fail thresholds (`VALIDATION_PLAN.md` §2–3), and the go/no-go recommendation. | Gates whether and how M1 starts | Before M1 |
| 15 | Which narrow segment(s) to recruit for the experiment? (A testing choice; the broad vision is unchanged.) | Q1 of the strategic review | Before experiment |
| 16 | Does the experiment come before M1, or in parallel with technical groundwork? `ROADMAP.md` currently has no pre-build validation milestone. | Roadmap integrity | Before M1 |
| 17 | Who runs the experiment (recruiting, consent, interviews, coding) and where is participant data held? | Ethics, privacy, feasibility | Before experiment |
| 18 | Should "currency/ledger" vocabulary be provisional until comprehension is tested (plain alternative as default in all mocks)? | Principle 3, Q4 | Before M4 copy |
| 19 | What are the success criteria for a plain-wording vs. currency-wording comparison? | H8 | Before experiment |
| 20 | Is a two-reviewer coding scheme for guilt/pressure in free text acceptable, or is a validated scale preferred? | Measurement quality | Before experiment |
