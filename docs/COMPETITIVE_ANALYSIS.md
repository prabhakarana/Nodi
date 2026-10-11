# Competitive Analysis (pre-build review)

**Observation date:** 2026-10-11
**Reviewer:** Claude (skeptical-strategist pass for Prompt 01)

## 0. Evidence quality — read this first

**Live product access was unavailable.** In this environment, direct fetches of `ravelo.app`, `apps.apple.com`, `opal.so`, `freedom.to`, and `api.freedom.to` failed (DNS resolution error; the outbound proxy returned 403 for a direct request). I did not install, open, or use any product.

All findings below come from **web-search result summaries** that quote or paraphrase primary pages (vendor sites, App Store listings, docs) or third-party reviews. I did not read any primary page in full. Therefore:

| Status | Meaning in this document |
|--------|--------------------------|
| **Verified** | Read directly on a primary source or by using the product. **None achieved in this pass.** |
| **Unverified** | Reported by a search summary of a primary or third-party source; not directly read. Treat as a lead, not a fact. |
| **Inferred** | My deduction from unverified claims. |

Absence of a feature in a summary is **not** evidence of absence. Every "not found" below means "not seen in the snippets", nothing more. Re-run this analysis with direct access before using any of it in positioning.

## 1. Established facts (about this review, not about the market)

- F1. The sources below were consulted on 2026-10-11 via search summaries only.
- F2. No product was used hands-on.
- F3. The claims table (§3) is entirely Unverified or Inferred.

## 2. Products reviewed

| Product | Category | Primary-source leads (not directly read) |
|---------|----------|------------------------------------------|
| Ravelo | Screen-time "banking" / attention credit | https://ravelo.app/ ; https://ravelo.app/faq ; https://apps.apple.com/us/app/ravelo-screen-time-banking/id6760021476 ; developer write-up https://dev.to/rakovskyyyy/what-if-your-screen-time-had-a-bank-account-i-spent-6-months-building-one-4a08 |
| Opal | Screen-time control / blocking / focus sessions | https://apps.apple.com/app/id1497465230 (listing); vendor site opal.so (not reachable) |
| Freedom | Session-based app/website blocker | https://api.freedom.to/features ; https://support.freedom.to/en/articles/5266497-freedom-for-families ; https://freedom.to/freedom-for-mac |
| RescueTime | Automatic time tracking | https://rescuetime.com/features ; https://api.rescuetime.com/features |
| ActivityWatch | Open-source local automatic tracker | https://activitywatch.net/ ; https://docs.activitywatch.net/en/latest/faq.html ; https://addons.mozilla.org/addon/aw-watcher-web/ |
| Toggl Track | Manual/timer time tracking | https://toggl.com/track/features/ ; https://docs.toggl.com/toggl-2.0-end-user-guide ; https://support.toggl.com/individual-user-guide |
| Attenya, Rascal (adjacent) | Focus-credit / earn-to-unlock | Surfaced incidentally in search; not examined. Named only so they are not forgotten. |

Not reviewed (gap): Screen Time (Apple), Digital Wellbeing (Google), Timeular, Clockify, Toggl Plan, Daily-planner/timeboxing apps, bullet-journal-style apps, Sunsama, Rize, Timing, Cold Turkey, One Sec, Stayfree. "Adjacent products" is wider than this list.

## 3. Capability observations

Dates are all 2026-10-11. "Source" is the lead URL; status per §0.

### Ravelo
| Claim | Status | Source |
|-------|--------|--------|
| iPhone app; minutes "deposited" by using designated useful apps (1:1) or off-phone focus sessions (15–120 min) | Unverified | App Store listing / FAQ via search |
| Earned minutes "withdrawn" in a "Time Market" to unlock leisure apps; lock returns at zero balance | Unverified | same |
| Distracting apps locked by default | Unverified | FAQ via search |
| Uses Apple DeviceActivity; ~15 min minimum purchase | Unverified | Developer write-up (dev.to) via search |
| Free tier: core currency + automatic blocking; Pro: custom categories, "advanced analytics", custom rates | Unverified | FAQ via search |
| Whether it offers daily intentions, planned-vs-actual comparison, reflection, weekly review, offline/manual entries, export, deletion | **Not seen in snippets — unknown** | — |
| Android / web availability | Unknown | — |

### Opal
| Claim | Status | Source |
|-------|--------|--------|
| iPhone app using Apple Screen Time API to block apps/sites | Unverified | App Store listing via search |
| Focus Sessions, "Deep Focus" (cannot be bypassed), time/open limits, reminders | Unverified | same |
| Free tier includes Focus Reports and a daily Focus Score | Unverified | Developer reply in App Store, via search |
| Data stays on device | Unverified | App Store listing via search |
| Desktop availability | Conflicting (third party says yes, listing says iPhone only) | techjockey vs. App Store |
| Intentions / planned-vs-actual / reflection | Not seen — unknown | — |

Note: a daily "Focus Score" is exactly the kind of scoring Nodi's constitution rules out; it is a design contrast, not a gap claim.

### Freedom
| Claim | Status | Source |
|-------|--------|--------|
| Session-based blocking of sites/apps/internet across Mac, Windows, iOS, Android, Chrome | Unverified | features page via search |
| Scheduled and recurring sessions; Locked Mode prevents ending sessions | Unverified | same |
| Session annotation, focus sounds | Unverified | same |
| Time-use history, intentions, reflection | Not seen — unknown | — |

### RescueTime
| Claim | Status | Source |
|-------|--------|--------|
| Automatic background tracking of apps, sites, documents | Unverified | features page via search |
| Custom goals with progress, alerts, weekly email report | Unverified | features page + third party |
| "Daily highlights" free-text notes about the day | Unverified | api.rescuetime.com/features via search |
| Never records keystrokes or page content; can pause tracking | Unverified | features page via search |
| CSV export requires premium | Unverified (third party only: Everhour) | Weak |
| Planned time-allocation vs. actual comparison | Not seen — unknown | — |

### ActivityWatch
| Claim | Status | Source |
|-------|--------|--------|
| Open source (MPL-2.0), free; data in local SQLite; nothing sent to cloud | Unverified | FAQ via search |
| Windows/macOS/Linux/Android; active-window and AFK watchers; Chrome/Firefox/Edge extensions; local web UI | Unverified | site + add-on page via search |
| Requires desktop app installed for the extension to work | Unverified | add-on page via search |
| Categories; cross-device sync "working on it" | Unverified | site via search |
| Intentions / reflection / manual entries | Not seen — unknown | — |

**Relevance:** if the claims hold, local-first automatic tracking with browser extensions already exists as open source. Nodi cannot claim local-first observation as novel.

### Toggl Track
| Claim | Status | Source |
|-------|--------|--------|
| Timer and manual entry modes | Unverified | features page + iOS listing via search |
| Goals (at least / less-than targets by project, task, tag, client) | Unverified; sources conflict on mobile support | Toggl 2.0 guide vs. Android support article |
| Reports filterable by period/project/client | Unverified | third-party review |
| Planned-vs-actual view | Not seen — unknown (Goals are the nearest feature) | — |

## 4. Honest synthesis

### 4.1 What appears already served (all Unverified)

- Earn-to-unlock attention currency: Ravelo; possibly Attenya, Rascal.
- Blocking and focus sessions: Opal, Freedom, Ravelo.
- Scores/reports on screen time: Opal (Focus Score/Reports).
- Automatic tracking with categories and goals: RescueTime, ActivityWatch.
- Manual entries, timers, and targets: Toggl Track.
- Local-first data: ActivityWatch (and Opal claims on-device).

### 4.2 What was *not seen* (and must not be treated as a confirmed gap)

- An explicit daily intention compared with actual time, across digital and offline life.
- A non-judgmental, whole-life (incl. rest, family, unclassified) account.
- Per-entry provenance (observed / manual / inferred / corrected).
- Reflection and weekly-review workflows tied to the ledger.

These are *candidates* for differentiation only. Many tools are likely to have a partial version (RescueTime goals + highlights, Toggl goals); the question is whether the *combination and framing* matter to users — which is a user question, not a desk-research one.

### 4.3 Inferences

- I1. Ravelo/Opal/Freedom are iPhone-first (Ravelo, Opal per listings) or blocker-first; a responsive web app competes on different surface and cannot offer OS-level observation. (Inferred.)
- I2. Competing on blocking/credit would be both off-constitution and a losing frame. (Inferred; consistent with Prompt 00 non-goals.)
- I3. Because tools in this space generally monetize via subscription and analytics tiers, "advanced analytics" is likely a crowded claim. (Inferred; weak.)

## 5. Verification checklist before any differentiation claim

For each of Ravelo, Opal, Freedom, plus RescueTime, Toggl Track, ActivityWatch, Apple Screen Time, Google Digital Wellbeing, and at least two timeboxing/planner tools:

1. Install or open the current version; record version, platform, date, and screenshots.
2. Does it let a user state an intention for the day/week *before* the time happens? In what unit?
3. Does it show intention vs. actual anywhere? How is the gap presented (neutral, scored, gamified)?
4. Can it record offline/non-device activity (manual entries, timers)?
5. Does it show data provenance, or silently merge sources?
6. Is there a reflection/review flow, and is it tied to the data?
7. Data location, export formats, deletion; read the privacy policy and store privacy labels.
8. Pricing and which of the above features are paywalled.
9. Read recent store reviews for unmet needs (record counts and quotes with dates, not impressions).
10. Search each vendor's help center/changelog for the *absent* features — do not infer absence from marketing pages.

Record results in this file with date, source, and Verified status.

## 6. Recommendations

- R1. Do not publish any "first", "only", or "unique" claim. (Already a constitution rule; reaffirmed.)
- R2. Treat the unified-ledger-with-intentions combination as the only candidate differentiator and test it with users (see `VALIDATION_PLAN.md`) before building more than a prototype.
- R3. Do not borrow Opal-style scores or Ravelo-style earn/lock mechanics, even as "engagement" features; both conflict with principle 3 and the non-goals.
- R4. Repeat this analysis with direct product access (a human with accounts/devices, or an environment with open network access) before M1 locks the data model.
