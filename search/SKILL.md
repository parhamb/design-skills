---
name: ux-search
description: >
  UX checklist and best practices for in-app search. Covers discoverability,
  autocomplete, filters, sort, empty states, voice search, and typo tolerance.
  Use when designing or reviewing a search feature, results page, or any
  content discovery flow.
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
| Empty state message | "No results for X" is paired with a spelling suggestion and related categories. |
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
