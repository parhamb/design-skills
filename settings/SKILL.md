---
name: ux-settings
description: >
  UX checklist and best practices for app settings screens. Covers settings
  organization, theme switching, font size, notification granularity, and data
  usage controls. Use when designing or reviewing a settings screen, preferences
  panel, or any configuration UI.
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
| Notification granularity | One toggle per notification type. Not just "All on / All off." |
| Data usage controls | Auto-download on Wi-Fi only by default. User controls media quality (low, standard, high). |
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
