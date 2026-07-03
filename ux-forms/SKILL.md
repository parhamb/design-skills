---
name: ux-forms
description: >
  Form design UX: input types, inline validation, keyboard behavior, autofill,
  password fields, auto-formatting, and multi-step flows. Use when designing
  or reviewing any form, sign-up flow, checkout, or data-entry screen.
---

# Forms UX

Forms are where intent turns into action. Every extra field, every ambiguous
label, and every delayed error message costs conversions and frustrates users.

---

## Checklist

| Item | Guidance |
|---|---|
| Minimal data collection | Only ask for what is needed right now. Defer optional fields to the profile. |
| Show / hide password | Eye icon on the right side of the password field. Hidden by default. |
| Multiple input methods | Offer voice or camera scan for fields where it genuinely helps (notes, documents). |
| Input suggestions | Autocomplete from history or a curated list to speed up data entry. |
| No repeated input | Pre-fill known data from the existing account. Never ask twice (WCAG 2.2 requires this — 3.3.7 Redundant Entry). |
| Password strength indicator | 4-level strength meter shown as the user types. Requirements listed inline. |
| Auto-format input | Format phone numbers, card numbers, and dates automatically as the user types. |
| Inline validation | Validate on blur (when the user leaves the field), not on final submit. |
| Correct keyboard type | Email field opens email keyboard. Number field opens number pad. URL field opens URL keyboard. |
| Enter key label | Return key shows "Next" to advance focus, or "Done" / "Search" when it submits. |
| Autofill support | Uses platform content type hints so password managers and autofill work correctly. |
| Form progress indicator | Multi-step forms show a step indicator ("Step 2 of 4") and allow going back. |

---

## Keyboard Type Reference

| Input | iOS contentType | Android inputType |
|---|---|---|
| Email | emailAddress | textEmailAddress |
| Phone | telephoneNumber | phone |
| One-time code | oneTimeCode | — |
| Full name | name | textPersonName |
| Password | password | textPassword |
| New password | newPassword | — |

---

## Patterns

**Progressive disclosure**: Split long forms into logical steps. No more than
5 to 6 fields per screen. Users abandon forms that look long before they start.

**Labels over placeholders**: Use visible labels above each field, not placeholder
text inside it. Placeholder text disappears on focus and creates accessibility issues.

**Smart defaults**: Pre-select the most common option. Pre-fill country from IP.
Pre-select the current year for expiry fields. Reduce the number of decisions the
user has to make.

**Error recovery**: If a form fails submission, scroll to the first error, keep
all previously entered data intact, and highlight the specific field that needs
attention. Never wipe the form clean on error.

---

## How to Review

When applying this checklist to a screen, flow, or codebase:

1. Go through every checklist item and mark it **Pass**, **Fail**, or **N/A** — never skip items silently.
2. Cite specific evidence for each finding: the screen, component, file, or line it applies to.
3. Tag each failure with a severity: **Blocker** (breaks the experience), **Major** (hurts usability), or **Minor** (polish).
4. End the review with the top 3 recommended fixes, ranked by user impact.

---

## Related Skills

- `ux-error-handling` — validation error patterns and error message formula
- `ux-content` — label and placeholder writing
- `ux-accessibility` — accessible authentication and redundant entry rules
