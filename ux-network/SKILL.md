---
name: ux-network
description: >
  Network and connectivity UX: offline mode, slow connection resilience,
  connection error states, background sync, caching strategy, and graceful
  degradation. Use when designing or reviewing how an app behaves under poor
  or absent network conditions.
---

# Network and Connectivity UX

Network conditions are unpredictable. An app that only works on fast Wi-Fi is
not a reliable product. Design for the worst connection and fast connections
will take care of themselves.

---

## Checklist

| Item | Guidance |
|---|---|
| Performance on slow connections | Critical content loads first. Images lazy-load. API payloads are compressed. |
| No internet error | Inline message with a retry button. Never an empty screen with no explanation. |
| Network switch resilience | App does not crash or disconnect when switching from Wi-Fi to mobile data. |
| Offline mode | Cached content is displayed. Writes are queued and flushed when connection returns. |
| Background data sync | Data syncs in background on Wi-Fi by default. User can enable sync over mobile data. |

---

## Offline-First Architecture

**Optimistic UI**: Update the UI immediately to show the expected outcome, then
sync in the background. If the sync fails, show an undo option. This approach
makes the app feel fast regardless of network speed.

**Cache strategies**:
- Stale-while-revalidate: Show cached content immediately, refresh in the background.
- Cache-first: Always show the cache, refresh only on explicit pull-to-refresh.
- Network-first: Try the network first, fall back to cache on failure.

**Sync queue**: Store pending writes locally and flush them when connectivity
returns. Show a clear sync status indicator so users know their changes are
queued and will be saved.

---

## Error State Patterns

| Scenario | UI Pattern |
|---|---|
| No internet at launch | Full-screen message with an illustration and a Retry button |
| Lost internet mid-use | Top banner: "No connection — working offline" |
| Slow connection | Skeleton screens instead of spinners |
| Server error (5xx) | "Something went wrong on our end." with a Retry button |
| Request timeout | "Taking longer than usual." with Keep waiting and Cancel options |
| Partial failure | Load what worked, show an inline error for what failed |

---

## Performance Targets

**Web (Core Web Vitals)**

| Metric | Target |
|---|---|
| Largest Contentful Paint (LCP) | Under 2.5 seconds |
| Interaction to Next Paint (INP) | Under 200ms |
| Cumulative Layout Shift (CLS) | Under 0.1 |

**Mobile app**

| Metric | Target |
|---|---|
| Cold start to interactive | Under 2 seconds |
| API response (P95) | Under 500ms |
| Offline cache hit | Under 100ms |
| Scrolling | No dropped frames at the display's refresh rate |

---

## How to Review

When applying this checklist to a screen, flow, or codebase:

1. Go through every checklist item and mark it **Pass**, **Fail**, or **N/A** — never skip items silently.
2. Cite specific evidence for each finding: the screen, component, file, or line it applies to.
3. Tag each failure with a severity: **Blocker** (breaks the experience), **Major** (hurts usability), or **Minor** (polish).
4. End the review with the top 3 recommended fixes, ranked by user impact.

---

## Related Skills

- `ux-error-handling` — error message writing and retry patterns
- `ux-help-onboarding` — loading indicators and skeleton screens
