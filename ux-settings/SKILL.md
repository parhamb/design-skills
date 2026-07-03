---
name: ux-settings
description: >
  Settings screen UX: settings organization and grouping, theme switching,
  font size, in-app language, notification granularity, cache clearing, and
  data usage controls. Use when designing or reviewing a settings screen,
  preferences panel, or any configuration UI.
---

# Settings UX

Settings is where users go when the defaults do not fit their life. A well-designed
settings screen increases retention. An overwhelming or buried one drives frustration.

---

## Checklist

| Item | Guidance |
|---|---|
| Logical grouping | Grouped by theme: Account, Notifications, Appearance, Privacy, About. |
| Theme switching | Offers System (auto), Light, and Dark options. A three-way segmented control works well. |
| Font size | Respects the OS setting by default. Offers an in-app override for accessibility needs. |
| In-app language | User can change the app language from within Settings, independent of the OS language. |
| Notification granularity | One toggle per notification type. Not just "All on / All off." See `ux-notifications`. |
| Data usage controls | Auto-download on Wi-Fi only by default. User controls media quality (low, standard, high). |
| Clear cache | User can clear the app cache and see storage usage from within Settings. |
| Section access | Settings serves as secondary navigation. Does not duplicate the main navigation. |
| Search in settings | Apps with 20 or more settings items offer a search bar inside settings. |
| Destructive actions at the bottom | Delete account, sign out, and similar actions appear at the bottom of the list. |

---

## Standard Settings Structure

```
Settings
├── Account / Profile
│   ├── Edit profile
│   ├── Change email or phone
│   └── Password and security
├── Notifications
│   ├── [Type 1] on/off
│   ├── [Type 2] on/off
│   └── Notification schedule
├── Appearance
│   ├── Theme (System / Light / Dark)
│   ├── Font size
│   └── Language
├── Privacy
│   ├── Data and permissions
│   ├── Download my data
│   └── Connected apps
├── Storage
│   ├── Storage usage
│   └── Clear cache
├── About
│   ├── Version number
│   ├── Privacy policy
│   ├── Terms of service
│   └── Open-source licenses
└── Danger zone
    ├── Sign out
    └── Delete account
```

---

## Patterns

**Immediate save**: Settings apply instantly without a "Save" button. The
exception is a form with multiple related fields where confirmation is needed,
such as changing an email address.

**Live preview**: When the user changes a visual setting like theme or font size,
show the result immediately without requiring them to leave the Settings screen.

**Contextual reset**: Each settings section offers a "Reset to defaults" option
rather than only a global reset that affects everything at once.

**Platform conventions**: On iOS, use a navigation list with the `.insetGrouped`
style and disclosure chevrons. On Android, use `PreferenceFragmentCompat` with
Material You styling. On web, a left sidebar works well for complex settings,
tabs for simpler apps.

---

## How to Review

When applying this checklist to a screen, flow, or codebase:

1. Go through every checklist item and mark it **Pass**, **Fail**, or **N/A** — never skip items silently.
2. Cite specific evidence for each finding: the screen, component, file, or line it applies to.
3. Tag each failure with a severity: **Blocker** (breaks the experience), **Major** (hurts usability), or **Minor** (polish).
4. End the review with the top 3 recommended fixes, ranked by user impact.

---

## Related Skills

- `ux-notifications` — per-type notification controls in depth
- `ux-user-account` — account section content and deletion flows
- `ux-general` — version number, dark mode sync, and OS language sync
