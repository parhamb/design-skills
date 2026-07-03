---
name: ux-information-architecture
description: >
  Information architecture (IA): content categorization, labeling, screen
  titles, sort and filter, settings structure, data hierarchy, and minimizing
  cognitive load. Use when designing app structure, auditing content
  organization, creating a sitemap, or improving how information is grouped
  and labeled.
---

# Information Architecture (IA)

IA is the practice of organizing, structuring, and labeling content so users
can find what they need. Poor IA is the invisible reason users say "I just
couldn't find it."

---

## Checklist

| Item | Guidance |
|---|---|
| Content categorization | Group by user mental models, not the internal org chart or database structure. |
| Well-structured content | Maximum 2 levels of hierarchy in any list. Never nest deeper than that. |
| Screen titles | Every screen has a clear, descriptive title that matches the nav item that opened it. |
| Sort options | Default sort is the most useful (date, relevance). User can change it. |
| Filter options | Active filter count shown ("3 filters active"). All filters can be cleared in one tap. |
| Minimal scrolling | Critical information is visible without scrolling. Details load progressively. |
| Timestamp visibility | Relative time near the event ("2 hours ago"), full timestamp accessible on tap. |
| Settings organization | Settings are grouped by theme: Account, Notifications, Privacy, Appearance, About. |
| F-pattern layout | Most important content is at the top and left of each screen. |
| Quick checkout | Purchase flow is 5 steps or fewer. Guest checkout is available. |

---

## IA Research Methods

**Card sorting**: Run an open card sort with 10 to 15 representative users before
finalizing category labels. Use the results to name categories with the words
users actually choose, not internal terminology.

**Tree testing**: Validate your structure by asking users to find items in a
text-only tree with no visual design. If users fail to find items in the tree,
the IA is the problem — not the visual design.

**First-click testing**: Research shows that 85% of users who click correctly
on their first attempt go on to complete the task. Test key flows with first-click
tests before investing in full prototypes.

---

## Labeling Principles

Use words your users use, not what your engineers or product managers call
things internally. Avoid jargon and acronyms for first-time users. Keep
navigation labels to 1 or 2 words. Be consistent — if one section is called
"Saved," do not call the same concept "Bookmarks" elsewhere in the app.

---

## How to Review

When applying this checklist to a screen, flow, or codebase:

1. Go through every checklist item and mark it **Pass**, **Fail**, or **N/A** — never skip items silently.
2. Cite specific evidence for each finding: the screen, component, file, or line it applies to.
3. Tag each failure with a severity: **Blocker** (breaks the experience), **Major** (hurts usability), or **Minor** (polish).
4. End the review with the top 3 recommended fixes, ranked by user impact.

---

## Related Skills

- `ux-navigation` — how the structure is surfaced to users
- `ux-search` — search as a complement to browsing
- `ux-content` — labeling and terminology consistency
