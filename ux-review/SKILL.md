---
name: ux-review
description: >
  Entry point for full UX reviews, design audits, and product feedback. Use
  when asked to review a screen, flow, feature, or entire app; audit UX or
  design quality; or give structured product feedback. Routes to the category
  skills that apply and defines the shared review output format.
---

# UX Review (Router)

A real UX review almost never fits inside one category. A single screen can
raise visual, accessibility, content, and error-handling issues at the same
time. This skill maps the request to the category skills to read, and defines
the output format every review follows.

---

## Review Process

1. **Identify the scope**: a single screen, a flow (onboarding, checkout), a
   feature (search, notifications), or the whole app.
2. **Select the category skills** using the routing table below. Read every
   skill that applies — most reviews need 3 to 5.
3. **Apply each checklist**: mark every item **Pass**, **Fail**, or **N/A**
   with specific evidence (screen, component, file, or line).
4. **Report** using the output format below.

---

## Routing Table

| What is being reviewed | Skills to read |
|---|---|
| Any screen (always) | `ux-visual-design`, `ux-accessibility`, `ux-content` |
| Onboarding / first run | `ux-help-onboarding`, `ux-user-account`, `ux-safety-privacy` |
| Login / sign-up / auth | `ux-user-account`, `ux-forms`, `ux-safety-privacy` |
| Forms / checkout / data entry | `ux-forms`, `ux-error-handling`, `ux-information-architecture` |
| Search / discovery | `ux-search`, `ux-information-architecture` |
| Navigation / app structure | `ux-navigation`, `ux-information-architecture` |
| Settings / preferences | `ux-settings`, `ux-notifications`, `ux-safety-privacy` |
| Errors / offline / edge cases | `ux-error-handling`, `ux-network` |
| Notifications | `ux-notifications`, `ux-settings` |
| AI features / automation | `ux-ai-automation`, `ux-content` |
| Sharing / favorites / power features | `ux-utility` |
| Whole app / store readiness | `ux-general` plus every category the app's surfaces touch |

---

## Output Format

Structure every review like this:

1. **Summary** — 2 to 4 sentences: overall quality, the biggest risk, the
   biggest strength.
2. **Findings by category** — one section per skill applied, containing a
   table: `Item | Verdict (Pass / Fail / N/A) | Evidence | Severity`.
   Severity is **Blocker** (breaks the experience), **Major** (hurts
   usability), or **Minor** (polish).
3. **Top fixes** — the 3 to 5 highest-impact changes, ranked, each with a
   concrete recommendation (not just a restatement of the problem).

Keep verdicts honest: if something cannot be verified from the material
provided (e.g. screen reader behavior from a static screenshot), mark it
**N/A — needs testing** rather than guessing.

---

## Review Principles

- **Evidence over opinion**: every Fail cites where it happens.
- **Severity over volume**: 5 ranked issues beat 50 unranked ones.
- **User impact framing**: describe what the user experiences, not just what
  rule is violated.
- **Acknowledge what works**: reviews that only list problems lose the
  reader's trust in the calibration of the findings.
