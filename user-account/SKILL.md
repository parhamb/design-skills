---
name: ux-user-account
description: >
  UX checklist and best practices for user account flows. Covers login, logout,
  social sign-in, gestures, shortcuts, learnability, success feedback, and
  account deletion. Use when designing or reviewing authentication, user profiles,
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
| Push notification opt-out | Per-category toggles in Settings. Do not reduce it to a single on/off switch. |
| Forgot password | Email link or SMS OTP. Links expire after 15 minutes. |
| Thumb-friendly key actions | Primary call to action is always within the bottom 40% of the screen. |
| Gesture support | Swipe-to-delete is supported with an undo snackbar immediately after. |
| Custom gestures | User can define custom gestures for frequently used actions. |
| Custom shortcuts | User can define personal shortcuts to key screens or actions. |
| 10-second comprehension | A first-time user understands the core value of the app within 10 seconds. |
| Ad removal option | User can pay to remove ads where applicable. |
| Password manager support | Password fields allow paste and use correct content type hints. |
| Purchasable features | In-app purchases and upgrades are clearly surfaced at the right moment. |
| Browse without account | Users can explore content without registering. The value wall comes after the value. |
| Last activity saved | App restores the user's last position or in-progress action on relaunch. |
| In-app operation status | Progress of ongoing actions (downloading, uploading) is visible while they run. |
| Cancel any action | Every async operation shows a cancel option while it is in progress. |
| Pull-to-refresh | Pulling down a list refreshes the content with a standard spinner animation. |
| Success feedback | A toast or snackbar confirms low-stakes actions. A modal confirms high-stakes ones. |
| Delete account | Account deletion is available and removes all associated data. Required by Apple and GDPR. |
| Password manager support | Password manager autofill works on all login and registration fields. |
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
