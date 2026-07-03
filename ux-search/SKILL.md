---
name: ux-search
description: >
  In-app search UX: discoverability, autocomplete, recent searches, filters,
  sort, no-results states, voice search, and typo tolerance. Use when designing
  or reviewing a search feature, results page, or any content discovery flow.
---

# Search UX

Search is often the fastest path to content. A poor search experience is one
of the most common reasons users churn from content-heavy apps.

---

## Checklist

| Item | Guidance |
|---|---|
| Search discoverability | Search bar is visible on the home screen or one tap away. Never buried in a menu. |
| Recent searches | Last 5 to 10 queries are saved. User can delete individual entries. |
| Search suggestions | Autocomplete appears after 1 to 2 keystrokes. Debounced at ~300ms. |
| Filter and sort | Filter chips appear above results. Active filter count shown in a badge. |
| Empty state message | "No results for X" is paired with a spelling suggestion and related categories. General empty-state standards live in `ux-error-handling`. |
| Search scope indicator | UI makes it clear what is being searched ("Searching in Orders"). |
| Voice search | Microphone icon in the search bar. Uses platform speech recognition APIs. |
| Typo tolerance | Fuzzy matching handles common spelling mistakes gracefully. |

---

## Patterns

**Progressive disclosure**: Show the top 3 results inline with a "See all" link
rather than sending users to a full results page for every query.

**Federated search**: When the app has multiple content types, group results by
type (People, Products, Documents) with clear section headers. Let users filter
to a specific type if needed.

**Blank state suggestions**: When the search bar is empty, show trending or
personalized suggestions rather than a blank box. This reduces the cognitive load
of starting a search from scratch.

**Zero-result analytics**: Track every search that returns no results. These
queries are a direct signal of content gaps or labeling mismatches.

**Search scope clarity**: If the search applies to a subset of content, say so
upfront. Users who search in a filtered context and get no results often blame
the app, not the active filter.

---

## How to Review

When applying this checklist to a screen, flow, or codebase:

1. Go through every checklist item and mark it **Pass**, **Fail**, or **N/A** — never skip items silently.
2. Cite specific evidence for each finding: the screen, component, file, or line it applies to.
3. Tag each failure with a severity: **Blocker** (breaks the experience), **Major** (hurts usability), or **Minor** (polish).
4. End the review with the top 3 recommended fixes, ranked by user impact.

---

## Related Skills

- `ux-information-architecture` — labeling and categorization that make search findable
- `ux-error-handling` — canonical empty-state standards
- `ux-ai-automation` — AI-powered and natural language search
