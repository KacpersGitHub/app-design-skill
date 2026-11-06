# Motion, haptics and sound

Timing values live in [tokens.md](tokens.md).

## What motion is for

Motion explains change. Each animation should answer one of:
- **Where did this come from / go to?** (a sheet slides from the button that opened it; a deleted item collapses its gap)
- **Did that work?** (press feedback, success check, a level filling up)
- **What's happening?** (skeleton shimmer, descriptive progress)
- **What can I do here?** (a subtle idle hint on an untouched option)

If it answers none of these, it's decoration. Cut it or keep it to a single signature moment.

## Every app should have

- **Press feedback** on everything tappable: slight scale-down (~0.96–0.98) or opacity change, instant on touch, spring back on release.
- **State-change animation** for toggles, selections, counters and progress (the number rolls, the bar fills, the check draws).
- **Spatial transitions:** push for going deeper, sheet for temporary tasks, fade for swapping content in place. Keep direction consistent.
- **Success moment** after meaningful actions; bigger celebrations only for real milestones.
- **Skeleton loading** shaped like the real content.
- **List changes animated:** inserted items expand in, deleted items collapse out.
- **Interruptible gestures:** anything dragged follows the finger, can be reversed mid-way, and settles with the release velocity.

## Motion quality bar

- Smooth at the device's refresh rate; animate transform and opacity rather than layout where possible.
- Springs for anything touch-driven; no bounce for routine UI, a little for playful or celebratory moments.
- Nothing blocks input: users can tap through or interrupt any animation.
- Respect reduced-motion settings: replace movement with fades or instant changes.

## Characters and mascots

- Interface motion (sliders, liquid levels, bubbles, progress, ripples) is best built as code-driven animation: interactive, crisp at any size, tiny.
- Character motion (jumping, swimming, waving) looks stiff and puppet-like when hand-built from moving parts. Use properly authored animation assets instead (frame-based vector animation, or short video with transparency), and keep the files small.
- Static or gently floating characters work well as vector art with simple code transforms.
- Give the mascot reactions to the user's actions (cheers on success, idle when nothing happens) so it feels alive.

## Delight that earns its place

- Idle wiggle on unselected onboarding options to invite the first tap.
- Scenes that react to device tilt or touch on first open ("this app is alive").
- Interactive onboarding where users try the core action before signing up.
- One signature animation tied to the app's core action (water filling a glass, a flame growing with a streak).
- Keep delight to the core loop and milestones; settings screens don't need it.

## Haptics

Haptics are one of the clearest signals of a premium app. Map each to meaning and use consistently:

| Moment | Haptic |
|--------|--------|
| Picker/slider passes a value, segmented control changes | Selection tick (lightest) |
| Toggle, button for a key action, card snaps into place | Light impact |
| Drag drop, pull-to-refresh threshold, sheet snaps | Medium impact |
| Action succeeded (saved, logged, purchased) | Success notification |
| Validation failed, action blocked | Error notification |
| Something needs attention | Warning notification |

- Fire at the exact moment of the visual change.
- Don't haptic on every tap, scroll, or continuous motion — it numbs the user.
- Pair, don't replace: haptics confirm visual feedback, never carry meaning alone.
- Android devices vary widely; prefer the system's predefined haptic types over raw vibration, and keep them rarer.
- Respect the system setting for haptics.

## Sound

- Optional, subtle, short; only on key actions (log, complete, celebrate).
- Respect the silent switch/ringer mode and offer a setting to turn sounds off.
