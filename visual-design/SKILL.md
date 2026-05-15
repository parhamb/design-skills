---
name: ux-visual-design
description: >
  UX checklist and best practices for mobile and web visual design. Covers
  typography, color, spacing, icons, animation, dark mode, empty states, touch
  targets, and RTL layout. Use when reviewing or creating a visual design system,
  auditing UI quality, or establishing component and token guidelines.
---

# Visual Design

Visual design is not decoration — it is communication. Every spacing decision,
color choice, and animation tells the user what matters and what to do next.

---

## Checklist

| Item | Guidance |
|---|---|
| Touch target size | Minimum 44x44pt on iOS, 48x48dp on Android. Non-negotiable for all tappable elements. |
| Empty state UI | Every empty screen shows an illustration or icon, a heading, a short message, and an optional action. |
| Font readability | Body text at minimum 16sp. Captions no smaller than 12sp. Line height between 1.4 and 1.6. |
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
| space-12 | 48pt | Minimum touch target |

---

## Typography Scale

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
