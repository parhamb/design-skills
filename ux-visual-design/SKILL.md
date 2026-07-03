---
name: ux-visual-design
description: >
  Visual design system review: typography, color, spacing, icons, animation,
  dark mode, empty states, touch targets, and RTL layout for mobile and web.
  Use when reviewing or creating a visual design system, auditing UI quality,
  or establishing component and token guidelines.
---

# Visual Design

Visual design is not decoration — it is communication. Every spacing decision,
color choice, and animation tells the user what matters and what to do next.

---

## Checklist

| Item | Guidance |
|---|---|
| Touch target size | Minimum 44x44pt on iOS, 48x48dp on Android. Non-negotiable for all tappable elements. |
| Empty state UI | Every empty screen shows an illustration or icon, a heading, a short message, and an optional action. Full standards live in `ux-error-handling`. |
| Font readability | Body text at 16–17sp. Supporting text (subhead, footnote, caption) no smaller than 12sp. Line height between 1.4 and 1.6. |
| Semantic color usage | Green for success, red for errors and destructive actions, yellow for warnings. Consistent throughout. |
| Error color differentiation | Error, warning, and info states are visually distinct from each other, not just color-coded. |
| Text hierarchy | Maximum 3 levels: title, body, caption. Use weight and size to differentiate, not color alone. |
| Design consistency | Every component and screen looks like it belongs to the same family. |
| Active and inactive states | Active vs inactive is communicated through color change or opacity, never color alone. |
| Row spacing | Minimum 8pt padding between list items. Content rows between 56dp and 72dp tall. |
| Micro-interactions | Button press feedback in under 100ms. Meaningful animations on state changes. |
| Avoid excessive animation | Animations are capped at 300ms for transitions. Reduced for lower-end hardware. |
| RTL and LTR layout | Layout mirrors correctly for right-to-left languages. Directional icons flip. |
| 8pt grid system | All spacing values are multiples of 4 or 8 (margin, padding, icon size, gap). |
| Notch and Dynamic Island | Background color extends into the safe area. Notch is not cut off. |
| Dark mode | Dark mode uses a dedicated color palette with elevated surfaces, not just an inverted light theme. |
| Image zoom | Users can view images at full size. Pinch-to-zoom is supported. |
| Image gallery | Swipe between images is supported where multiple images are shown. |
| Consistent dialogs | Alert and modal dialogs are styled the same way across the entire app. |
| Universal icons | Icons carry meaning without requiring a label for most users. |
| Screen transition animation | Screen transitions use smooth, directional animations that reinforce navigation hierarchy. |

---

## Spacing Tokens

| Token | Value | Common use |
|---|---|---|
| space-1 | 4pt | Icon gap, tight padding |
| space-2 | 8pt | Inline padding, list item gap |
| space-3 | 12pt | Component inner padding |
| space-4 | 16pt | Section padding, standard margin |
| space-6 | 24pt | Card padding, screen edge margin |
| space-8 | 32pt | Section separator gap |
| space-12 | 48pt | Large section gap |

Touch target minimums (44x44pt iOS, 48x48dp Android) are hit-area sizes,
not spacing tokens — a small icon may keep its visual size as long as its
tappable area meets the minimum.

---

## Typography Scale (iOS, HIG-derived)

| Role | Size | Weight |
|---|---|---|
| Display | 34sp | Bold |
| Title 1 | 28sp | Bold |
| Title 2 | 22sp | Semibold |
| Headline | 17sp | Semibold |
| Body | 17sp | Regular |
| Callout | 16sp | Regular |
| Subhead | 15sp | Regular |
| Footnote | 13sp | Regular |
| Caption | 12sp | Regular |

## Typography Scale (Android, Material 3)

| Role | Size | Weight |
|---|---|---|
| Headline Medium | 28sp | Regular |
| Title Large | 22sp | Regular |
| Title Medium | 16sp | Medium |
| Body Large | 16sp | Regular |
| Body Medium | 14sp | Regular |
| Label Large | 14sp | Medium |
| Label Small | 11sp | Medium |

Use the scale native to each platform rather than forcing one scale on both.
Roles below Body (subhead, footnote, caption, labels) are supporting text —
the 16sp readability minimum in the checklist applies to body copy.

---

## Patterns

**Color as a secondary signal**: Never use color as the only way to
communicate state. Always pair color with an icon, label, or shape so
color-blind users get the same information.

**Consistent elevation**: Use shadow and surface color to communicate
layers — overlays, cards, and sheets should each have a clearly distinct
elevation level. This is especially important in dark mode.

**Reduce-motion awareness**: Check the OS reduce-motion setting and
disable or simplify decorative animations when it is enabled. Motion
should never be the only way to communicate state change.

---

## How to Review

When applying this checklist to a screen, flow, or codebase:

1. Go through every checklist item and mark it **Pass**, **Fail**, or **N/A** — never skip items silently.
2. Cite specific evidence for each finding: the screen, component, file, or line it applies to.
3. Tag each failure with a severity: **Blocker** (breaks the experience), **Major** (hurts usability), or **Minor** (polish).
4. End the review with the top 3 recommended fixes, ranked by user impact.

---

## Related Skills

- `ux-accessibility` — contrast ratios, text scaling, and reduce-motion requirements
- `ux-content` — the words inside the components
- `ux-error-handling` — canonical empty-state standards
