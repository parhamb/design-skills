---
name: ux-notifications
description: >
  Notification UX: push permission timing, per-type granularity, quiet hours,
  badge accuracy, deep-link targets, notification content quality, grouping
  and channels, and in-app notification centers. Use when designing or
  reviewing push notifications, notification settings, or any messaging that
  interrupts the user.
---

# Notifications UX

A notification interrupts someone's life. Every one you send spends trust, and
the balance is easy to overdraw: the OS-level "turn off all notifications"
switch is one long-press away, and once flipped it almost never comes back.

---

## Checklist

| Item | Guidance |
|---|---|
| Permission timing | Ask after the user has experienced value, tied to a feature that needs it — never on first launch. |
| Pre-permission prompt | An in-app screen explains what notifications the user will get before the system dialog appears. |
| Per-type granularity | One toggle per notification type (orders, messages, promotions). Never a single on/off switch. |
| Transactional vs promotional | Marketing notifications are opt-in and separate from transactional ones. Disabling promotions never disables receipts or security alerts. |
| Quiet hours | User can set a do-not-disturb schedule, or the app respects the OS Focus / DND modes. |
| Badge accuracy | App icon badge count matches actual unread items and clears when they are viewed. |
| Deep-link target | Tapping a notification lands on the exact relevant content, never the home screen. |
| Notification content | Specific and actionable: "Sara replied to your comment", not "You have a new notification." |
| Grouping | Multiple notifications from the same source collapse into a group or summary. |
| Android channels | Every notification type has its own channel so users can control them at the OS level. |
| In-app notification center | A history of past notifications is available in the app for anything the user missed or dismissed. |
| Frequency capping | Promotional notifications are rate-limited. Sending caps are enforced per user, per day. |

---

## Permission Strategy

**Contextual ask**: Request permission at the moment the value is obvious —
after the user places an order ("Get delivery updates?"), follows a topic, or
sends a first message. Acceptance rates for contextual asks are several times
higher than launch-time asks.

**Pre-permission screen**: Show your own explainer first. If the user declines
your screen, you keep the ability to ask again later; if they decline the
system dialog, you may never get another chance (iOS allows the system prompt
only once).

**iOS provisional authorization**: Consider `provisional` authorization to
deliver notifications quietly to the Notification Center without any prompt —
the user upgrades or disables them after seeing real examples.

**Graceful denial**: If the user declines, keep the app fully functional and
offer an in-app notification center instead. Provide a path to enable later
("Turn on in Settings > Notifications").

---

## Content Guidelines

- Front-load the payload: the first ~40 characters must carry the message.
- Write like a person, not a system: "Your ride is 2 minutes away."
- Never use clickbait or fake urgency; it earns one tap and loses the channel.
- Include the actor and the object: who did what to what.
- Support rich content (images, actions) where it saves the user an app launch —
  "Reply", "Mark as done", "Track order" as inline actions.

---

## How to Review

When applying this checklist to a screen, flow, or codebase:

1. Go through every checklist item and mark it **Pass**, **Fail**, or **N/A** — never skip items silently.
2. Cite specific evidence for each finding: the screen, component, file, or line it applies to.
3. Tag each failure with a severity: **Blocker** (breaks the experience), **Major** (hurts usability), or **Minor** (polish).
4. End the review with the top 3 recommended fixes, ranked by user impact.

---

## Related Skills

- `ux-settings` — where notification controls live and how they are grouped
- `ux-safety-privacy` — permission prompt best practices
- `ux-navigation` — deep links that notifications land on
- `ux-content` — notification copy quality
