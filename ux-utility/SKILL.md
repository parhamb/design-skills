---
name: ux-utility
description: >
  Utility and productivity features: favorites, bookmarks, native share sheet,
  in-app browser, personalization, and clipboard integration. Use when designing
  or reviewing features that help users get things done faster or customize
  their experience.
---

# Utility Features

Utility features are what keep power users loyal. They reduce repetitive work
and let users shape the app around their own habits and preferences.

---

## Checklist

| Item | Guidance |
|---|---|
| Favorites and bookmarks | Save icon visible on content cards. Saved list is easy to find from the main navigation. |
| Share feature | Uses the native share sheet. Never a custom share UI. Includes a shareable URL. |
| In-app browser | External links may open in an in-app browser, but always with a visible "Open in browser" action. Respect the user's default browser for external destinations — never trap users in the in-app view. |
| Personalization | User can choose interests, layout, or notification frequency, starting at onboarding. |
| Clipboard integration | Copied URLs are detected on app launch and offered to the user as a quick action — using privacy-safe detection APIs (see pattern below). |

---

## Patterns

**Share sheet**: Pre-populate the share text with a useful message, not a bare
URL. Include UTM parameters for tracking. Support sharing images, text, and
URLs through the same entry point.

**Favorites architecture**: Save to local storage first, then sync to the server.
Never fail silently. Show a fill animation on save as confirmation. Empty state
for the saved list should invite the first save action. Optionally allow organizing
saved items into folders for power users.

**Personalization strategies**: Start with an explicit onboarding step where users
select their interests. Refine over time with behavioral signals (views, time spent,
taps). Always show a "Why am I seeing this?" explanation so recommendations feel
trustworthy rather than arbitrary.

**Clipboard detection**: Show a subtle, non-intrusive banner when a link is
detected on the clipboard: "We noticed a link — open it in [App]?" Dismiss
automatically after a few seconds if the user ignores it. Never open the link
automatically.

Platform constraints: on iOS 16+, reading the clipboard directly triggers a
system paste permission prompt — use `UIPasteboard.detectPatterns` to check
whether a URL is present without reading the contents and without triggering
the prompt. Android 12+ shows a system toast whenever an app reads the
clipboard, so read it only at the moment of use, never speculatively.

---

## How to Review

When applying this checklist to a screen, flow, or codebase:

1. Go through every checklist item and mark it **Pass**, **Fail**, or **N/A** — never skip items silently.
2. Cite specific evidence for each finding: the screen, component, file, or line it applies to.
3. Tag each failure with a severity: **Blocker** (breaks the experience), **Major** (hurts usability), or **Minor** (polish).
4. End the review with the top 3 recommended fixes, ranked by user impact.

---

## Related Skills

- `ux-general` — widgets, integrations, and cross-platform parity
- `ux-safety-privacy` — clipboard and permission privacy expectations
- `ux-ai-automation` — personalization driven by recommendations
