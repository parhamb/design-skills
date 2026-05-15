---
name: ux-general
description: >
  UX checklist and best practices for general app quality. Covers app store
  presence, launch experience, platform compatibility, cloud sync, OS integrations,
  and versioning. Use when reviewing overall app health, preparing for store
  submission, or evaluating cross-platform consistency.
---

# General App Quality

These are the fundamentals every app needs regardless of domain. Reviewers,
users, and store guidelines all expect them.

---

## Checklist

| Item | Guidance |
|---|---|
| App name | Memorable, spellable, searchable. Check for trademark conflicts before launch. |
| App icon | Recognizable at 29x29pt. No text inside the icon. Works on both light and dark backgrounds. |
| App icon (PWA) | Appropriate icon configured for PWA installation and homescreen display. |
| Installation guide | User is clearly informed about the install or activation process. |
| ASO | Keyword-rich title, subtitle, and description. A/B test screenshots regularly. |
| What's new | Changelog or release notes are shown to the user after an update. |
| Splash screen | Brand-colored background with a centered logo. Keep it under 2 seconds. |
| Force update | Mandatory update dialog blocks old versions with a clear store link. |
| Cloud sync | Data syncs across devices. Has a defined conflict resolution strategy. |
| Backup and restore | User can back up and fully restore data on reinstall. |
| OS language sync | App language updates automatically when the OS language changes. |
| Dark mode sync | App follows the OS dark mode setting without requiring manual change. |
| Background mode | App continues working in the background where needed (audio, timers). |
| Widget support | Homescreen widget is available for quick access to core actions. |
| Storage location | User can move data between internal storage and SD card (Android). |
| In-app rating prompt | Store rating prompt appears at the right moment — after a clear user win. |
| In-app language | User can change the app language from within Settings. |
| Clear cache | User can clear app cache from within the app. |
| Contact support | A clear way to reach the support team is available inside the app. |
| App integrations | App can connect to third-party services where relevant. |
| Cross-platform parity | Core functionality is consistent across all supported platforms. |
| Version number | App version is visible in Settings or About. |
| Trial mode indicator | Users on a trial see their trial status and expiry clearly. |
| Status bar activity | Background activity (music, recording) is visible in the system status bar. |
| Multitasking support | App handles split screen and simultaneous actions without breaking. |
| Orientation support | App works correctly in both portrait and landscape orientations. |

---

## Key Principles

**Ship-ready baseline**: The items above are table stakes, not nice-to-haves.
If any of them fail, the app is not ready for production.

**Platform conventions matter**: iOS and Android users have different mental models.
Follow each platform's own guidelines rather than porting one platform's patterns to another.

**Test on real devices**: Simulators miss orientation bugs, performance issues, and
real-world storage behavior. Always test the final build on physical hardware before submission.

**Update cadence**: A "What's new" section only works if updates are meaningful
and communicated in plain language — not "Bug fixes and performance improvements."
