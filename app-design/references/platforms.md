# Platforms: iOS and Android

Design one product with the same identity on both, but let each platform's conventions win where users have muscle memory.

## Conventions that differ

| | iOS | Android |
|---|-----|---------|
| Back | Swipe from left edge; back button top-left | System back gesture/button (including predictive back preview) — never trap it |
| Primary navigation | Bottom tab bar | Bottom navigation bar or navigation rail |
| Top bar | Large title that collapses on scroll | Top app bar, title left or centered |
| Main action | In the content or top-right | Can be a floating action button |
| Dialogs | Alerts and action sheets | Material dialogs and bottom sheets |
| Typeface | SF Pro | Roboto / Google Sans |
| Touch target | 44×44pt | 48×48dp |
| Screen edges | Safe areas around notch/Dynamic Island and home indicator | Edge-to-edge drawing behind system bars; respect insets |
| System look | Translucent, glassy materials on bars and controls | Dynamic color from the user's wallpaper, expressive shapes |

Rules:
- Keep brand, layout, content and core flows identical. Adapt navigation, back behavior, dialogs and system controls (date pickers, share sheet, switches) to each platform.
- Use system share, photo picker, and authentication (passkeys, Sign in with Apple / Google) instead of custom versions.
- Respect safe areas/insets on every screen; nothing important under the notch, island or gesture bar.

## Widgets, live activities and ongoing notifications

Add these when the app tracks something over time (habits, timers, deliveries, workouts, countdowns, progress). They bring users back without opening the app.

**iOS**
- **Live Activity** for something happening right now: on the Lock Screen and in the Dynamic Island. Design all presentations: **minimal** (tiny, shared with another activity), **compact** (two sides of the island), **expanded** (long-press), and the **Lock Screen** banner.
- **Home Screen / Lock Screen widgets** in the standard sizes (small, medium, large; lock screen circular/rectangular/inline).
- Show one key value (progress, time remaining, next step) plus at most one action. Buttons can perform the action directly (log, pause, complete) without opening the app.
- Follow Apple's size, padding and font limits; keep animations within the system's allowed transitions.

**Android**
- **Home-screen widgets** in resizable grid sizes; follow the user's dynamic color.
- **Ongoing / progress notifications** (shown as Live Updates on newer Android versions) for something happening now, with a progress indicator and up to a few actions.
- Same content rules: one key value, one or two actions.

**Both**
- Reuse the app's visual identity (accent color, mascot or core object, e.g. a glass filling up).
- Stay useful when the app is closed: countdown to next action, today's progress, streak.
- Add a settings toggle to turn the live activity / ongoing notification on or off, with a short description and a preview of what it looks like.
- Respect the system's dark and tinted widget appearances.

## Notifications

- Ask for permission after showing the value of reminders, ideally after the user sets one up.
- Let users choose time and frequency; default to fewer.
- Each notification is specific and actionable ("You're 300 ml from today's goal"), never generic ("We miss you!").
- Group by channel/category so users can mute one type without muting all.
