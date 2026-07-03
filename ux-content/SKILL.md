---
name: ux-content
description: >
  Content strategy and UX writing: plain language, microcopy, labeling,
  read/unread states, localization, and content freshness. Use when writing
  or reviewing UI copy, error messages, empty states, tooltips, onboarding
  text, or any in-product content.
---

# Content and UX Writing

Every word in your UI is a design decision. Good UX writing reduces friction,
builds trust, and guides users to their next step. It carries the same weight
as visual design.

---

## Checklist

| Item | Guidance |
|---|---|
| Plain language | Write at a 7th-grade reading level. Short sentences and common words. |
| Data accuracy | User-entered data is validated and shown back correctly. No stale values. |
| UGC distinction | User-generated content is in a visually distinct container from editorial content. |
| Read and unread indicators | Read and unread items are visually differentiated with a bold title or a colored dot. |
| Localization quality | Translations are reviewed by native speakers. Machine translation alone is not sufficient. |
| Content freshness | Outdated content is flagged, archived, or removed after a defined threshold. |

---

## UX Writing Principles

**Be specific, not vague**
- Avoid: "Something went wrong."
- Use: "We couldn't save your photo. Check your connection and try again."

**Write for the action, not the object**
- Avoid: "Submit"
- Use: "Create account" / "Send message" / "Place order"

**Front-load the key information**
- Avoid: "To complete your order, please enter your card details below."
- Use: "Enter your card details to complete the order."

**Be consistent with terminology**
Pick one word for one concept and use it everywhere. If one screen says "Save"
another should not say "Store" or "Keep" for the same action.

---

## Microcopy Patterns

| Context | Pattern |
|---|---|
| Button | Verb plus noun: "Download report", "Add photo" |
| Destructive button | Specific verb: "Delete account", not "OK" |
| Placeholder text | A genuine hint, not a repeated label: "Search by city or ZIP" |
| Error message | What happened and how to fix it |
| Success message | Confirm the action and suggest the next step |
| Loading text | What is loading: "Uploading photo..." not just "Loading..." |
| Empty state headline | Empathetic and forward-looking (full standards in `ux-error-handling`) |

---

## Localization Notes

Strings should never be concatenated. Use placeholders: "Hello, %@" not "Hello, " + name.
Leave 30 to 40% expansion space for German, Finnish, and Russian translations.
Date, time, number, and currency formats are locale-specific — always use platform
formatters, never hardcode them. Right-to-left languages require layout mirroring,
not just a text direction change.

---

## How to Review

When applying this checklist to a screen, flow, or codebase:

1. Go through every checklist item and mark it **Pass**, **Fail**, or **N/A** — never skip items silently.
2. Cite specific evidence for each finding: the screen, component, file, or line it applies to.
3. Tag each failure with a severity: **Blocker** (breaks the experience), **Major** (hurts usability), or **Minor** (polish).
4. End the review with the top 3 recommended fixes, ranked by user impact.

---

## Related Skills

- `ux-error-handling` — the error message formula and empty-state standards
- `ux-forms` — labels, placeholders, and validation copy
- `ux-accessibility` — plain language as an accessibility requirement
