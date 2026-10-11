# Open Questions

Unresolved product and technical decisions. Do not resolve silently: when answered, move the outcome to `docs/DECISIONS.md` and mark the item resolved here.

| # | Question | Why it matters | Needed by |
|---|----------|----------------|-----------|
| 1 | ~~Technology stack~~ **Partly resolved by D-006:** Apple-first native long term (SwiftUI assumed, not yet confirmed); throwaway web tool now. **Still open:** the web tool's stack (suggestion: TypeScript + Vite, minimal, disposable) and the shared-core approach (Swift-only vs. Rust/Kotlin Multiplatform). | Shapes M1 | M1 |
| 2 | Which local persistence mechanism (for the throwaway web tool: browser storage is acceptable; for native: e.g. SwiftData/Core Data/SQLite — undecided) (e.g. IndexedDB, localStorage, other)? Storage limits and data-loss behavior on browser clear? | Local-first promise, export importance | M1 |
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
| 21 | Is native device-wide automatic tracking in scope? The vision currently allows only a later optional browser extension (D-008). Requires owner approval after the Apple feasibility spike and privacy review. | Constitution scope | Before any native observer work |
| 22 | **Draft ready for review** (`docs/EVENT_SCHEMA.md`, `docs/schema/`). Accept, amend, or reject the schema (D-007): fields, ID scheme, time zones, correction model, export format, versioning. Sub-decisions are #27–#34. | Data survives web tool → native | Before the web tool is built |
| 23 | Apple Screen Time feasibility spike: what data can an app actually obtain, and what entitlements and review are needed? (Read current Apple docs; build a minimal proof of concept.) | iOS/iPadOS automatic tracking may be impossible or limited | Before committing to automatic tracking on Apple devices |
| 24 | Native stack details: SwiftUI-only vs. UIKit/AppKit mix; minimum OS versions; shared core language; how Android and Windows are staffed later. | Long-term architecture | Before native build |
| 25 | What is the migration path for diary/web-tool data into the native app (import of the D-007 format)? | Continuity of user data | Before native build |
| 26 | Does sync between a user's Apple devices come in (e.g. via the user's own iCloud) or stay out as a non-goal? | Cross-device cloud sync is currently a non-goal | Before native build |
| 27 | Overlap precedence: user-authored > observed > inferred, and user-vs-user overlaps flagged rather than auto-resolved (EVENT_SCHEMA §7). Accept? (Refines #5.) | Honest accounting, no double-counting | Before the web tool is built |
| 28 | Do `inferred` entries count in the account before the user accepts them? Proposal: no. | Principle 7 | Before inference is built |
| 29 | Is domain-level observation acceptable by default for browser/native observers, or must the user opt in per domain? | Principle 6 | Before any observer |
| 30 | Is the 24-hour day the base for "unaccounted time", or waking hours? Does a user-defined day start apply? (Refines #4.) | Account correctness | Before the web tool is built |
| 31 | Should `target.comparison` include `at_most`, or does a cap read as a limit/penalty and conflict with principle 3? | Principle 3 | Before intentions are built |
| 32 | Can the user purge correction history without deleting the entry? | Provenance vs privacy | Before export/delete |
| 33 | Do user-created rules (`user_rule`) ship in the first version, or only manual categories? | Scope | Before the web tool is built |
| 34 | Future-time tolerance for entries (clock skew) and maximum interval length? | Data quality | Before the web tool is built |
