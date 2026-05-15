---
name: ux-safety-privacy
description: >
  UX checklist and best practices for app safety and privacy. Covers biometric
  authentication, permission prompts, 2FA, GDPR compliance, data protection,
  multi-device management, and notification controls. Use when designing or
  auditing authentication, data handling, permissions, or any security-sensitive flow.
---

# Safety and Privacy UX

Privacy is a user right. Security is a promise. Both must be designed for
explicitly — users should not have to choose between convenience and protection.

---

## Checklist

| Item | Guidance |
|---|---|
| Biometric authentication | Face ID and fingerprint are available for app re-entry and sensitive actions. |
| Storage permission prompt | Asked at the moment of use, not on launch. Explains why access is needed. |
| Location permission prompt | Request "While Using" first. Upgrade to "Always" only when strictly necessary. |
| Permissions listed | All required permissions are explained before the system dialog appears. |
| Data protection | Data is encrypted at rest and in transit. Sensitive fields are masked. |
| Multi-device management | User can view all signed-in devices and revoke access remotely from Settings. |
| Notification management | Per-type notification toggles (transactional, promotional, security). |
| Two-factor authentication | TOTP (authenticator app) available with SMS as fallback and backup codes for recovery. |
| Privacy policy link | Accessible from Settings > About and during account creation. A link, not a buried PDF. |
| GDPR compliance | Data export, data deletion, and consent management are implemented. |
| Analytics disclosure | Analytics providers are listed in the privacy policy. |

---

## Permission Best Practices

Ask for permissions in context, not on launch. Requesting camera access when
the user first opens the app feels invasive. Asking when the user taps the
camera icon feels natural and logical.

Before the system permission dialog appears, show a pre-permission screen that
explains what you are asking for and why. This dramatically improves the
acceptance rate and reduces the chance the user denies and never comes back.

If a user denies a permission, always provide a recovery path. Show a message
like "Enable in Settings > [App] > Camera" rather than silently disabling the feature.

---

## GDPR Requirements and UX Implications

| Requirement | UX implementation |
|---|---|
| Right to access | "Download your data" option in Account settings |
| Right to erasure | "Delete account and all data" flow with confirmation |
| Right to portability | Data exported in a machine-readable format (JSON or CSV) |
| Consent | Separate opt-in for marketing. Pre-ticked checkboxes are not valid consent. |
| Data minimization | Collect only what is used. Delete what is no longer needed. |
| Privacy by default | The most private settings are the default, not the most permissive. |

---

## Authentication Security Patterns

**Passkeys (FIDO2)**: Most secure with the best UX. Resistant to phishing.
Use as the primary option where supported.

**TOTP 2FA**: Authenticator app (Google Authenticator, Authy). 6-digit rotating codes.

**SMS OTP**: More accessible but vulnerable to SIM swap. Use as a fallback, not a primary.

**Magic links**: Passwordless email login. Single-use and expire after 15 minutes.

**Biometrics**: Local authentication only. Biometric data never leaves the device.
