# Validation Plan and Pre-Build Strategic Review

**Date:** 2026-10-11
**Status:** Proposal. Thresholds and numbers below are suggestions from the reviewer and require product-owner approval (see `docs/OPEN_QUESTIONS.md`).

Labels: **Fact** = established from repository or this review's evidence; **Hypothesis** = unvalidated belief; **Recommendation** = proposed action.

## 1. Skeptical review of the seven questions

### Q1. Is the user problem specific enough to design an MVP?
- **Fact:** The target is deliberately broad: "people who feel their time slips away" (`PRODUCT_VISION.md` §2). No user research exists.
- **Assessment:** Not yet. "Feels time slips away" describes a feeling, not a behavior, context, or trigger. It spans students, shift workers, parents, remote workers, people with ADHD — who differ in what "time slipping" means (lost evenings to scrolling? unplanned hours at work? no energy left for family?). A broad audience is fine for a *vision* but a poor basis for *design decisions* (default categories, tone, entry friction).
- **Recommendation:** Keep the broad vision; pick one or two narrow recruiting segments for the experiment (e.g., people who say they lose their evenings or weekends). This is a testing choice, not a redefinition of the audience. Record the choice in `DECISIONS.md` when made.

### Q2. What is already served?
See `docs/COMPETITIVE_ANALYSIS.md` §4. Summary (all Unverified): earn-to-unlock currency and blocking (Ravelo and others), focus sessions and scores (Opal), session blockers (Freedom), automatic tracking with goals (RescueTime, ActivityWatch), manual/timer tracking with targets (Toggl). Plain time logging, timers, categories, and local storage are table stakes, not differentiators.

### Q3. What must be verified before making differentiation claims?
See `COMPETITIVE_ANALYSIS.md` §5, a ten-point checklist. Key point: this pass had **no direct access** to any product, so nothing is Verified. Specifically unknown: whether any of these tools offers intentions, planned-vs-actual, reflection, or provenance.

### Q4. Is a personal attention ledger understandable without verbal explanation?
- **Hypothesis (H4):** a "personal currency" metaphor makes time tangible.
- **Risks (reasoned, not observed):** "ledger", "account", "currency", and "spend" import financial and scarcity framing that may feel like pressure — in tension with "awareness without guilt" — and may suggest time has a price. "Ledger" may also read as accounting jargon to non-enthusiasts.
- **Recommendation:** Test comprehension *before* building: show 5–8 people a static mock of a daily account with no explanation, then ask them to say in their own words what it shows and how it makes them feel. Also test a plain alternative ("Today's time" with no currency vocabulary). Currency framing is not accepted until it beats or matches the plain version.

### Q5. Does intended-vs-actual add value beyond ordinary time tracking?
- **Hypothesis (H3):** yes, because the gap makes decisions visible.
- **Counter-hypotheses the experiment must be able to confirm:** (a) people do not set intentions consistently; (b) gaps are uninteresting or demoralizing; (c) a plain log changes behavior as much; (d) intentions are made in vague terms that cannot be compared; (e) the effort of logging dominates any benefit.
- **Assessment:** Unproven. Existing goal features (Toggl, RescueTime) suggest the comparison is not unknown, so novelty cannot be the argument; value to the user must be.

### Q6. Privacy and technical limits of hybrid web + browser-extension tracking?
(Reasoned from search summaries of vendor and developer pages; Unverified, and to be checked against current official Chrome/Firefox/Safari docs.)
- A web page cannot observe other tabs, other apps, or offline activity. The web app must keep its "manual and timer only" honesty (already in the constitution).
- An extension sees only the browser, not other applications, and not the phone. A unified ledger across "digital and offline life" therefore still depends on manual entry for most of life.
- URL/domain observation is sensitive (health, finance, relationships). It needs opt-in, an explainable allow/deny model, local-only storage by default, domain-level rather than full-URL capture, easy pause, and visible deletion.
- Manifest V3 service workers can be stopped at any time and lose in-memory state; reliable tracking needs timestamps persisted in extension storage and event-driven computation rather than polling (sources disagree on idle timeout; Unverified).
- Extension and web-app local storage are separate origins; a handoff mechanism (messaging permission, import/export, or native messaging) is required and has its own permission and review costs.
- Store review and permissions (e.g., `tabs`, host permissions) may add friction and user distrust; Safari and mobile browsers differ.
- Open-source precedent (ActivityWatch, Unverified) suggests local-first automatic tracking is feasible but also that it requires a separate installed component.
- **Recommendation:** Keep the extension out of the experiment entirely. Revisit only if the manual-first experiment succeeds.

### Q7. Smallest experiment that can disprove the main hypothesis?
See §3.

## 2. What we are testing

**Primary hypothesis (H1/H3, restated falsifiably):** For people who feel their time slips away, using a single daily record that pairs a stated intention with what actually happened leads them to make at least one deliberate change to how they allocate time, more than a plain record of what happened does.

**Disproved if** (proposed thresholds, to be approved before the experiment starts):
- fewer than ~half of participants in the intention-vs-actual condition report a specific deliberate change in week 2, **or** that rate is not meaningfully higher than the plain-log condition;
- most participants stop logging within the first week (logging effort outweighs value);
- participants report the comparison as guilt-inducing or irrelevant more often than useful.

With ~10–20 participants, results are **directional only**; the experiment is designed to kill a weak idea cheaply, not to prove a strong one.

## 3. Smallest disproving experiment (no app code)

**Format:** A 14-day diary study using existing tools (shared spreadsheet or a plain notes template, plus a daily prompt by message/email). No Nodi software.

**Participants:** 10–20 people recruited from the chosen narrow segment(s), who say they feel their time slips away. Mix of non-enthusiasts; exclude people already using a time-tracking system daily.

**Conditions (random assignment):**
- **A – Plain log:** record what you did each day (manual entries + optional timer from phone clock).
- **B – Intend vs. actual:** write 1–3 intentions each morning in their own words; log what happened; at end of day, note the gap in one sentence (no scoring, no prescribed categories).

**Everyone:** same end-of-day question ("anything you'd do differently tomorrow?") and a weekly review prompt in week 1 and 2. Provenance: participants mark entries as remembered, timed, or corrected later, so we learn if provenance matters.

**Measures (all self-reported or counted; none invented in advance as "targets" beyond §2):**
- Logging adherence (days logged / 14).
- Count of deliberate changes reported (specific, behavioral).
- Emotional valence of the gap (free text, coded by two reviewers).
- Time cost per day (self-reported minutes).
- Comprehension and wording friction (which words they use for time, categories, rest).
- Exit interview (20 min): would you keep doing this? what would you pay attention to? what felt wrong?

**Decision after the experiment (to be recorded in `DECISIONS.md`):**
- Go to a local-first prototype if B clearly outperforms A on deliberate change *and* adherence is adequate.
- Pivot framing if B works but the currency vocabulary confuses or pressures.
- Stop or re-scope if B shows no benefit over A or causes guilt.

**Ethics/privacy:** voluntary, informed consent, data kept by the participant until they choose to share, delete on request, no sensitive-site capture.

**Cost:** days of recruiting plus ~2 weeks elapsed; effectively zero engineering.

## 4. Optional second experiment (only if the first passes)

A throwaway single-page prototype (no persistence beyond local storage) to test: entry friction, timer usability, and the daily-account view comprehension (Q4). Still no extension.

## 5. What this plan does not do

- It does not validate market size, willingness to pay, or retention beyond 14 days.
- It does not test automatic tracking or the extension.
- It does not replace direct competitor verification (`COMPETITIVE_ANALYSIS.md` §5).

## 6. Go / no-go recommendation

**Recommendation:** **No-go on building the full local-first MVP now. Go on the 14-day diary experiment (and the competitor verification pass) first.**

Reasoning:
- The core differentiation is unproven, and this review could not verify competitor capabilities at all (§0 of the competitive analysis).
- The audience is not specific enough to make MVP design choices defensibly (Q1).
- The riskiest assumptions (the currency metaphor, the value of the intention gap, guilt-free presentation) can be tested for almost no engineering cost.
- Nothing is lost by waiting: the M1 technical decisions (stack, storage) do not depend on the outcome, but the data model and copy do.

If the experiment passes the thresholds approved in advance, proceed to M1–M2 with the narrowed segment recorded. If it fails, revisit the constitution rather than quietly drifting toward blocking or gamification.
