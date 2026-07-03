---
name: ux-accessibility
description: >
  Accessibility (a11y) audit checklist: WCAG 2.2 compliance, screen reader
  support (VoiceOver, TalkBack), color contrast, touch targets, motor
  impairment, reduce-motion, and focus management. Use when auditing
  accessibility, implementing assistive technology support, or designing
  for inclusive use.
---

# Accessibility (A11y)

Accessibility is not a checklist to finish — it is a quality bar that benefits
every user. Good contrast helps users in sunlight. Large touch targets help
users on a moving bus. Clear labels help distracted users. Build for the edges
and the center benefits too.

---

## Checklist

| Item | Standard | Guidance |
|---|---|---|
| WCAG 2.2 AA compliance | WCAG 2.2 | Current standard since October 2023. AA is the legal bar in most regions, including under the European Accessibility Act (in force since June 2025). |
| Color contrast (text) | WCAG 1.4.3 (AA) | 4.5:1 ratio for normal text. 3:1 for large text (18sp or 14sp bold). |
| Color contrast (UI components) | WCAG 1.4.11 (AA) | 3:1 ratio for icons, borders, and focus indicators. |
| Touch target size | WCAG 2.5.8 (AA) | WCAG 2.2 minimum is 24x24 CSS px. Platform guidelines are stricter and should be the design target: 44x44pt (Apple HIG), 48x48dp (Material). The 44px criterion (2.5.5) is AAA. |
| Screen reader support | — | All interactive elements have accessibility labels. Custom actions replace gesture shortcuts. |
| Focus management | WCAG 2.4.3 (A) | Tab and D-pad focus order is logical. Focus moves to new content after navigation. |
| Focus not obscured | WCAG 2.4.11 (AA) | The focused element is never fully hidden behind sticky headers, footers, or overlays. |
| Color blindness safe | WCAG 1.4.1 (A) | Color is never the only differentiator. Pair with icons, shapes, or labels. |
| Reduce motion | WCAG 2.3.3 (AAA) | Check OS reduce-motion setting. Simplify or disable decorative animations. AAA formally, but a platform expectation on iOS and Android. |
| Adjustable text size | Platform | Supports Dynamic Type (iOS) and sp units (Android). Tested at 200% size. |
| Dark and light mode | — | Both themes independently meet contrast requirements. |
| Motor impairment | — | Switch Control (iOS) and Switch Access (Android) work on all interactive elements. |
| Accessible authentication | WCAG 3.3.8 (AA) | Login never depends on memorizing or transcribing (e.g. cognitive puzzles). Paste and autofill always allowed. |
| Redundant entry | WCAG 3.3.7 (A) | Information already entered in a flow is auto-populated or selectable, never asked twice. |
| Thumb zone | — | Critical actions are within natural thumb reach in the bottom 40% of the screen. |

---

## WCAG Levels

| Level | Meaning |
|---|---|
| A | Minimum. Failing these makes the app unusable for many users. |
| AA | Legal standard in most regions. Industry target. |
| AAA | Enhanced. Not always achievable for all content types. |

---

## New in WCAG 2.2

| Criterion | Level | Summary |
|---|---|---|
| 2.4.11 Focus Not Obscured (Minimum) | AA | Focused elements are at least partially visible |
| 2.5.7 Dragging Movements | AA | Drag actions have a single-pointer alternative |
| 2.5.8 Target Size (Minimum) | AA | Targets are at least 24x24 CSS px |
| 3.2.6 Consistent Help | A | Help mechanisms appear in the same place on every screen |
| 3.3.7 Redundant Entry | A | Never ask for the same information twice in one flow |
| 3.3.8 Accessible Authentication (Minimum) | AA | No cognitive function tests to log in |

---

## Platform APIs Reference

**iOS**: `accessibilityLabel` (what VoiceOver reads), `accessibilityHint` (what it does),
`accessibilityTraits` (.button, .header, .link), `UIAccessibility.isReduceMotionEnabled`,
`UIFont.preferredFont(forTextStyle:)` for Dynamic Type.

**Android**: `contentDescription` (TalkBack label), `importantForAccessibility`
(include or exclude from accessibility tree), `AccessibilityManager.isEnabled()`
to detect TalkBack, `sp` units for text that scales with user font size settings.

---

## Testing Approach

Test every primary flow with the screen reader enabled and your eyes closed.
If you cannot complete the flow without looking at the screen, it fails the
accessibility requirement. This is the single most effective test you can run.

Use Accessibility Inspector (Xcode) and Accessibility Scanner (Android) for
automated audits, but treat them as a starting point. Automated tools catch
roughly 30% of real accessibility issues. The rest require manual testing.

---

## How to Review

When applying this checklist to a screen, flow, or codebase:

1. Go through every checklist item and mark it **Pass**, **Fail**, or **N/A** — never skip items silently.
2. Cite specific evidence for each finding: the screen, component, file, or line it applies to.
3. Tag each failure with a severity: **Blocker** (breaks the experience), **Major** (hurts usability), or **Minor** (polish).
4. End the review with the top 3 recommended fixes, ranked by user impact.

---

## Related Skills

- `ux-visual-design` — contrast, touch targets, and reduce-motion in the design system
- `ux-content` — plain language and label clarity
- `ux-forms` — accessible validation and input hints
