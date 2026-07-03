---
name: ux-user-account
description: >
  User account and authentication UX: login, logout, social sign-in and SSO,
  password recovery, session management, gestures and shortcuts, and account
  deletion. Use when designing or reviewing authentication, user profiles,
  account settings, or any interaction that requires a signed-in user.
---

# User Account UX

The account experience spans from first login to long-term retention. Every
friction point in authentication is a potential drop-off. Every confusing
account flow erodes trust.

---

## Checklist

| Item | Guidance |
|---|---|
| Social and SSO login | Sign in with Apple is required on iOS if any social login exists. Google is standard everywhere. |
| Logout confirmation | One dialog with a clear consequence: "You will need your password to sign back in." |
| Push notification opt-out | Per-category toggles in Settings. Do not reduce it to a single on/off switch. See `ux-notifications`. |
| Forgot password | Email link or SMS OTP. Links expire after 15 minutes. |
| Thumb-friendly key actions | Primary call to action is always within the bottom 40% of the screen. |
| Gesture support | Swipe-to-delete is supported with an undo snackbar immediately after. |
| Custom gestures | User can define custom gestures for frequently used actions. |
| Custom shortcuts | User can define personal shortcuts to key screens or actions. |
| Password manager support | Autofill works on all login and registration fields. Password fields allow paste and use correct content type hints. |
| Browse without account | Users can explore content without registering. The value wall comes after the value. |
| Last activity saved | App restores the user's last position or in-progress action on relaunch. |
| Success feedback | A toast or snackbar confirms low-stakes actions. A modal confirms high-stakes ones. |
| Delete account | Account deletion is available and removes all associated data. Required by Apple and GDPR. |
| Location access | App requests location only when a feature genuinely needs it, with a clear reason. |

---

## Patterns

**Progressive sign-up**: Let users experience the core value of the app before
asking for an account. Prompt for sign-up only when the user tries to save, share,
or access personalized content. This consistently outperforms a hard login wall.

**Persistent session**: Use refresh tokens to keep users logged in silently.
Never force a re-login simply because an access token expired. Handle token
refresh invisibly in the background.

**Biometric re-entry**: Require biometric confirmation (Face ID, fingerprint)
to re-enter the app after a background period, not just at first login.
This balances security with convenience.

**Graceful post-logout state**: After logging out, return the user to the
home or sign-in screen with a clear path back in. Never leave them on a
broken or blank screen.

---

## How to Review

When applying this checklist to a screen, flow, or codebase:

1. Go through every checklist item and mark it **Pass**, **Fail**, or **N/A** — never skip items silently.
2. Cite specific evidence for each finding: the screen, component, file, or line it applies to.
3. Tag each failure with a severity: **Blocker** (breaks the experience), **Major** (hurts usability), or **Minor** (polish).
4. End the review with the top 3 recommended fixes, ranked by user impact.

---

## Related Skills

- `ux-safety-privacy` — biometrics, 2FA, passkeys, and permission prompts
- `ux-forms` — input types, validation, and autofill on auth forms
- `ux-settings` — account section structure and destructive action placement
- `ux-notifications` — notification opt-in timing and granularity
