---
name: ux-error-handling
description: >
  UX checklist and best practices for error handling. Covers destructive action
  confirmation, undo, empty states, descriptive error messages, crash recovery,
  and server error handling. Use when designing or reviewing error states,
  confirmation dialogs, undo flows, or any screen that needs to handle failure.
---

# Error Handling UX

Every error is a broken promise. How you handle it determines whether the user
forgives you or leaves. Good error handling is preventive, informative, and
always leaves a path forward.

---

## Checklist

| Item | Guidance |
|---|---|
| Destructive action confirmation | Single dialog. Action button is styled red. Cancel appears on the left. |
| Undo action | Snackbar with an "Undo" button for 5 to 7 seconds after deletions and moves. |
| Empty state screens | Every empty screen shows an illustration, a message, and an optional action. |
| Reduce human error | Inputs are constrained, defaults are smart, and validation catches mistakes early. |
| Descriptive error messages | States what failed, why if relevant, and what the user can do next. |
| Crash recovery | App restores the previous state on relaunch after a crash. |
| Server error handling | 5xx and timeout errors show a human-readable message and a Retry button. |

---

## Error Message Formula

```
[What happened] + [Why, if it helps] + [What to do next]
```

Examples that work:
- "We couldn't save your post. Check your connection and tap Save again."
- "Your session expired. Sign in to continue."
- "This username is already taken. Try adding numbers or a different word."
- "Payment declined. Your card ending in 4242 was not charged. [Try another card]"

---

## Error Types and UI Patterns

| Error type | Pattern |
|---|---|
| Validation | Inline, below the field. Shown when focus leaves the field. |
| Recoverable server error | Toast or inline message with a Retry button |
| Blocking server error | Full-screen error page with Retry and Contact Support options |
| Auth error | Redirect to login. Preserve the user's intended destination. |
| Permission denied | Explain the issue and link to Settings to resolve it. |
| Network error | Top banner with offline mode fallback |
| Empty state | Positive framing with an invitation to act |
| Content not found (404) | Friendly message with suggestions and a path to Home |
| Crash | Offer to report the crash and restore the previous state |

---

## Confirmation Dialog Standards

Title should state the action and what it affects: "Delete conversation?"
Body should state the consequence: "This will permanently remove 48 messages."
The confirm button label should match the title verb: "Delete" in red.
Cancel should appear on the left, confirm on the right.

Never use "OK" or "Yes" as the label on a destructive confirm button.
Never reverse the button positions.

---

## Undo vs Confirm

| Use undo when | Use a confirm dialog when |
|---|---|
| The action can be reversed | The action is permanent or irreversible |
| The cost of a mistake is low | The cost of a mistake is high |
| Speed is important | The user should slow down and think |
| Example: archive a message | Example: delete an account |
