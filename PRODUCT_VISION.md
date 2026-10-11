# Nodi — Product Vision

**Product:** Nodi
**Tagline:** Every moment has value.
**Guiding principle:** Awareness without guilt.

This is the product constitution. All design, architecture, and implementation work must conform to it. Changes to this file require an explicit entry in `docs/DECISIONS.md`.

## 1. Vision

Nodi is a personal attention-accountability system for people who feel their time slips away.

It helps users:

1. Understand where their time goes.
2. Compare how they actually spent it with how they intended to spend it.
3. Decide how to allocate their attention more deliberately.

The central experience loop is:

**Intend → Observe → Account → Reflect → Adjust**

Nodi uses a personal currency metaphor to make time tangible. The metaphor is personal and illustrative. It must never imply that time has a universal monetary value, that rest is wasteful, or that productivity determines human worth.

## 2. Target audience

Begin broad: people who feel they lose track of their time. Nodi must be approachable for people who are not productivity enthusiasts. Avoid jargon, optimization culture, and assumptions of prior habit-tracking experience.

Narrower segments are an open question (see `docs/OPEN_QUESTIONS.md`); none is assumed.

## 3. Differentiating hypothesis

**Hypothesis (unvalidated):** A unified personal time ledger — combining manual entries, timers, and eventually permitted automatic digital-activity observations — can help people reconcile their actual time with their personal intentions across digital and offline life.

This is a hypothesis, not a proven competitive advantage. Never claim a capability is unique without evidence. Other products (for example Ravelo) already cover substantial parts of the attention-currency, focus-credit, and app-blocking space; Nodi must not make those its central value proposition.

## 4. Product principles

1. **User-defined priorities.** The user decides what matters.
2. **Whole-life accounting.** Work, family, learning, exercise, leisure, rest, and unclassified time all belong.
3. **Awareness without guilt.** Never shame, score, or moralize activities.
4. **Transparent provenance.** Distinguish observed, manually entered, inferred, and corrected data.
5. **User agency.** Automatic tracking must be optional and explainable.
6. **Privacy first.** Minimize collection, default to local storage where practical, and make export and deletion straightforward.
7. **Honest accounting.** Avoid double-counting, hidden corrections, and invented activity classifications.
8. **Progressive complexity.** Validate the simplest useful experience before adding integrations.

## 5. Scope

The initial product is a responsive web app for desktop and mobile.

> **Amended by D-006 (`docs/DECISIONS.md`):** the web app is a throwaway validation tool; the long-term product is native, Apple first. Automatic native tracking is not approved (D-008).

### Initial MVP

- Daily attention account
- Manual activity entries
- Start, pause, resume, and stop timers
- User-defined categories
- Daily intentions
- Daily allocation summary
- End-of-day reflection
- Weekly review
- Local persistence
- Editing, export, and deletion

### Later, optional

Automatic website/domain tracking via an optional browser extension. The web app must not claim to observe all activity across the device.

## 6. Non-goals

Unless separately approved and recorded in `docs/DECISIONS.md`, Nodi will not include:

- App blocking, or blocking as the main experience
- Earning minutes to unlock distracting apps as a central mechanic
- Treating productive time as inherently more valuable than leisure or rest
- Generic charts that do not help users make decisions
- Social leaderboards or public profiles
- AI coaching
- Paid subscriptions
- Cross-device cloud sync
- Scores, streak-shaming, or moral judgments of activities
- Claims of device-wide observation from the web app
