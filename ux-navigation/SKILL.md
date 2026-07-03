---
name: ux-navigation
description: >
  App navigation UX: tab bars, back buttons, deep links, gesture navigation,
  scroll behavior, modal vs push, and the 3-tap rule. Use when designing or
  auditing a navigation system, screen hierarchy, or information flow in a
  mobile or web app.
---

# Navigation UX

Navigation is the skeleton of the app. When it is invisible and predictable,
users feel in control. When it is broken or confusing, they leave.

---

## Checklist

| Item | Guidance |
|---|---|
| Home accessible anywhere | Logo or home tab always returns to the root screen from anywhere in the app. |
| Persistent navigation | Tab bar or bottom navigation is visible on all primary screens. |
| Max 3 taps to content | Any piece of content is reachable in 3 taps or fewer from the home screen. |
| Current location indicator | The active tab is highlighted. Deep screens show a breadcrumb or clear title. |
| Android back button | Follows the back stack correctly. Never exits the app unexpectedly. |
| Back button on every screen | Every pushed screen has a back or close button in the top-left corner. |
| Logical flow | Navigation order matches the user's mental model and task sequence. |
| Deep link support | Every major screen has a URI scheme or Universal Link for direct access. |
| Tab bar badge counts | Unread count badges are accurate and clear when the content is viewed. |
| Scroll padding | Content at the bottom is padded above the tab bar height and safe area. |
| Status bar visible | Status bar is shown during normal app use. Hidden only in full-screen media. |

---

## Navigation Patterns

**Bottom tab bar (iOS)**: 3 to 5 items maximum. Icon and label together.
Badge for notification counts. Not used for destructive actions.

**Side drawer (Android)**: Suitable for apps with 5 or more top-level sections.
Opened by a hamburger icon or a left-edge swipe. User avatar and name at the top.

**Top navigation bar**: Single screen title centered or left-aligned.
Action icons on the right, maximum 2 visible. Back or close on the left.

**Modal vs push**: Push (drill-down) is for content that is part of the
hierarchy. Modal (sheet or dialog) is for tasks that interrupt the main flow
such as creating, editing, or confirming something. Never push where you
should modal — it breaks the expected back stack behavior.

**Deep linking strategy**: Every major content screen should have a stable URL
or URI scheme. This enables sharing, notifications, and marketing links to
land users directly in the right place without going through the home screen.

---

## How to Review

When applying this checklist to a screen, flow, or codebase:

1. Go through every checklist item and mark it **Pass**, **Fail**, or **N/A** — never skip items silently.
2. Cite specific evidence for each finding: the screen, component, file, or line it applies to.
3. Tag each failure with a severity: **Blocker** (breaks the experience), **Major** (hurts usability), or **Minor** (polish).
4. End the review with the top 3 recommended fixes, ranked by user impact.

---

## Related Skills

- `ux-information-architecture` — the structure the navigation exposes
- `ux-notifications` — notifications that deep-link into the right screen
- `ux-general` — cross-platform navigation parity
