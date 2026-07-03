---
name: ux-general
description: >
  General app quality: app store presence, launch experience, splash screen,
  force update, cloud sync, backup and restore, OS integrations, widgets,
  orientation, monetization surfacing, and versioning. Use when reviewing
  overall app health, preparing for store submission, or evaluating
  cross-platform consistency.
---

# General App Quality

These are the fundamentals every app needs regardless of domain. Reviewers,
users, and store guidelines all expect them.

Each item carries a priority:

- **Required** — launch blocker. Failing this means the app is not production-ready.
- **Recommended** — strong quality signal. Most successful apps have it.
- **Optional** — differentiator. Valuable for specific audiences, not universal.

---

## Checklist

| Item | Priority | Guidance |
|---|---|---|
| App name | Required | Memorable, spellable, searchable. Check for trademark conflicts before launch. |
| App icon | Required | Recognizable at 29x29pt. No text inside the icon. Works on both light and dark backgrounds. |
| App icon (PWA) | Recommended | Appropriate icon configured for PWA installation and homescreen display. |
| Installation guide | Recommended | User is clearly informed about the install or activation process. |
| ASO | Recommended | Keyword-rich title, subtitle, and description. A/B test screenshots regularly. |
| What's new | Recommended | Changelog or release notes are shown to the user after an update. |
| Splash screen | Required | Brand-colored background with a centered logo. Keep it under 2 seconds. |
| Force update | Required | Mandatory update dialog blocks old versions with a clear store link. |
| Cloud sync | Recommended | Data syncs across devices. Has a defined conflict resolution strategy. |
| Backup and restore | Recommended | User can back up and fully restore data on reinstall. |
| OS language sync | Recommended | App language updates automatically when the OS language changes. |
| Dark mode sync | Recommended | App follows the OS dark mode setting without requiring manual change. |
| Background mode | Required where applicable | App continues working in the background where needed (audio, timers). |
| Widget support | Optional | Homescreen widget is available for quick access to core actions. |
| Storage location | Optional | User can move data between internal storage and SD card (Android). |
| In-app rating prompt | Recommended | Store rating prompt appears at the right moment — after a clear user win. |
| Contact support | Required | A clear way to reach the support team is available inside the app. |
| App integrations | Optional | App can connect to third-party services where relevant. |
| Cross-platform parity | Recommended | Core functionality is consistent across all supported platforms. |
| Version number | Required | App version is visible in Settings or About. |
| Trial mode indicator | Required where applicable | Users on a trial see their trial status and expiry clearly. |
| Status bar activity | Required where applicable | Background activity (music, recording) is visible in the system status bar. |
| Multitasking support | Recommended | App handles split screen and simultaneous actions without breaking. |
| Orientation support | Recommended | App works correctly in both portrait and landscape orientations. |
| In-app operation status | Required | Progress of ongoing actions (downloading, uploading) is visible while they run. |
| Cancel any action | Recommended | Every async operation shows a cancel option while it is in progress. |
| Pull-to-refresh | Recommended | Pulling down a list refreshes the content with a standard spinner animation. |
| Ad removal option | Optional | User can pay to remove ads where applicable. |
| Purchasable features | Recommended where applicable | In-app purchases and upgrades are clearly surfaced at the right moment. |

---

## Key Principles

**Ship-ready baseline**: Required items are table stakes — if any of them fail,
the app is not ready for production. Recommended and Optional items are quality
and retention levers, not launch blockers.

**Platform conventions matter**: iOS and Android users have different mental models.
Follow each platform's own guidelines rather than porting one platform's patterns to another.

**Test on real devices**: Simulators miss orientation bugs, performance issues, and
real-world storage behavior. Always test the final build on physical hardware before submission.

**Update cadence**: A "What's new" section only works if updates are meaningful
and communicated in plain language — not "Bug fixes and performance improvements."

---

## How to Review

When applying this checklist to a screen, flow, or codebase:

1. Go through every checklist item and mark it **Pass**, **Fail**, or **N/A** — never skip items silently.
2. Cite specific evidence for each finding: the screen, component, file, or line it applies to.
3. Tag each failure with a severity: **Blocker** (breaks the experience), **Major** (hurts usability), or **Minor** (polish).
4. End the review with the top 3 recommended fixes, ranked by user impact.

---

## Related Skills

- `ux-settings` — in-app language, cache clearing, and preference organization
- `ux-navigation` — deep links, back stack, and screen hierarchy
- `ux-notifications` — push permission timing and notification quality
- `ux-review` — entry point for a full multi-category UX audit
