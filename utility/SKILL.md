---
name: ux-utility
description: >
  UX checklist and best practices for utility and productivity features. Covers
  favorites, bookmarks, sharing, in-app browser, personalization, and clipboard
  integration. Use when designing or reviewing features that help users get things
  done faster or customize their experience.
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
| In-app browser | External links open in an in-app browser, not the system browser. User stays in the app. |
| Personalization | User can choose interests, layout, or notification frequency, starting at onboarding. |
| Clipboard integration | Copied URLs are detected on app launch and offered to the user as a quick action. |

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
