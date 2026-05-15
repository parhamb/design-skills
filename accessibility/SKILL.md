---
name: ux-accessibility
description: >
  UX checklist and best practices for mobile and web accessibility. Covers WCAG
  compliance, screen reader support, color contrast, touch targets, motor
  impairment, reduce-motion, and focus management. Use when auditing accessibility,
  implementing VoiceOver or TalkBack support, or designing for inclusive use.
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
| WCAG 2.1 AA compliance | WCAG 2.1 | Minimum acceptable bar. AA is the legal standard in most countries. |
| Color contrast (text) | WCAG 1.4.3 | 4.5:1 ratio for normal text. 3:1 for large text (18sp or 14sp bold). |
| Color contrast (UI components) | WCAG 1.4.11 | 3:1 ratio for icons, borders, and focus indicators. |
| Touch target size | WCAG 2.5.5 | 44x44pt minimum on iOS. 48x48dp on Android. |
| Screen reader support | — | All interactive elements have accessibility labels. Custom actions replace gesture shortcuts. |
| Focus management | WCAG 2.4.3 | Tab and D-pad focus order is logical. Focus moves to new content after navigation. |
| Color blindness safe | WCAG 1.4.1 | Color is never the only differentiator. Pair with icons, shapes, or labels. |
| Reduce motion | WCAG 2.3.3 | Check OS reduce-motion setting. Simplify or disable decorative animations. |
| Adjustable text size | Platform | Supports Dynamic Type (iOS) and sp units (Android). Tested at 200% size. |
| Dark and light mode | — | Both themes independently meet contrast requirements. |
| Motor impairment | — | Switch Control (iOS) and Switch Access (Android) work on all interactive elements. |
| Thumb zone | — | Critical actions are within natural thumb reach in the bottom 40% of the screen. |

---

## WCAG Levels

| Level | Meaning |
|---|---|
| A | Minimum. Failing these makes the app unusable for many users. |
| AA | Legal standard in most regions. Industry target. |
| AAA | Enhanced. Not always achievable for all content types. |

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
