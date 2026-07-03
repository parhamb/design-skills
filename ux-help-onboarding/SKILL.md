---
name: ux-help-onboarding
description: >
  Onboarding and help UX: first-run flows, loading states, skeleton screens,
  tooltips, contextual help, and in-app support. Use when designing or
  reviewing first-run experiences, feature discovery flows, contextual help,
  loading indicators, or in-app support.
---

# Help and Onboarding UX

Onboarding sets the trajectory of a user's entire relationship with the app.
A great first run converts. A confusing one churns. And once users are in,
good help systems make them feel confident rather than lost.

---

## Checklist

| Item | Guidance |
|---|---|
| 10-second comprehension | A first-time user understands the core value of the app within 10 seconds of first launch. |
| Loading indicator | Spinner or progress bar shown for anything taking longer than 400ms. |
| Skeleton screens | Used instead of spinners for content-heavy screens during loading. |
| Onboarding flow | Demonstrates value through experience, not a feature list. |
| Skip onboarding | A "Skip" option is visible on every onboarding step. |
| Contextual tooltip | Shown on first visit to a complex screen. One concept only. Easily dismissible. |
| In-app help center | Searchable help content within the app. Does not redirect to a website. |

---

## Loading State Guidelines

| Duration | Recommended pattern |
|---|---|
| Under 400ms | No indicator needed — feels instant |
| 400ms to 3 seconds | Skeleton screen (content-shaped placeholder) |
| 3 to 10 seconds | Progress bar with an estimated time remaining |
| Over 10 seconds | Background task with a push notification on completion |

**Skeleton screen design**: Match the shape of the real content — rectangles
for images, lines for text. Animate with a shimmer sweeping left to right.
Use 2 to 3 generic rows rather than matching the exact final count of items.

---

## Onboarding Patterns

**Value-first**: Show what the app does through demonstration before asking
for anything. Delay sign-up until the user has experienced something meaningful.
This consistently reduces early drop-off.

**Progressive**: Introduce features as users encounter them, not all at once.
Use tooltips and coach marks at the right contextual moment rather than a
long intro tutorial.

**Blank slate**: First-time empty screens actively invite the first action.
"Add your first task" beats an empty list with no direction. Full empty-state
standards live in `ux-error-handling`.

**Permissions**: Pre-permission screens explain why each permission matters
before the system dialog appears. Request permissions in sequence and only
when the feature that needs them is first used.

---

## Onboarding Do and Don't

| Do | Don't |
|---|---|
| Show, don't tell | List feature bullet points |
| One concept per screen | Overwhelm with all features at once |
| Show progress ("2 of 4") | Give no sense of how long onboarding is |
| Keep Skip visible on every step | Force completion of all steps |
| Let users revisit onboarding in Settings | Assume one viewing is enough |
| Personalize on the first step | Ask for an account before showing value |

---

## How to Review

When applying this checklist to a screen, flow, or codebase:

1. Go through every checklist item and mark it **Pass**, **Fail**, or **N/A** — never skip items silently.
2. Cite specific evidence for each finding: the screen, component, file, or line it applies to.
3. Tag each failure with a severity: **Blocker** (breaks the experience), **Major** (hurts usability), or **Minor** (polish).
4. End the review with the top 3 recommended fixes, ranked by user impact.

---

## Related Skills

- `ux-content` — onboarding copy and tooltip writing
- `ux-error-handling` — canonical empty-state standards
- `ux-safety-privacy` — permission prompt timing during onboarding
- `ux-notifications` — when to ask for notification permission
