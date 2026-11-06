# Accessibility and dark mode

Accessible apps are better apps for everyone: bigger targets, clearer text and honest labels help all users.

## Text size

- Support the system text size setting (Dynamic Type on iOS, font scale on Android), including the largest accessibility sizes.
- Layouts must reflow when text grows: no fixed-height text containers, rows grow vertically, horizontal layouts stack when they run out of room.
- Never truncate decision-critical text at large sizes; wrap instead.
- Only cap scaling for elements that can't grow (tab bar labels, tiny badges), and offer the full text another way (e.g. a long-press preview).
- Test every screen at the largest size before calling it done.

## Contrast and color

- Text ≥4.5:1; large text (18pt+, or 14pt bold) and meaningful icons/borders ≥3:1.
- Never use color as the only signal: pair status colors with an icon, label or pattern (errors get an icon and text, chart lines get labels).
- Placeholder text is not a label; keep a visible label above the field.

## Screen readers (VoiceOver, TalkBack)

- Every icon-only button has a spoken label describing the action ("Add drink", not "plus").
- Group related elements so a card reads as one item ("Margherita pizza, 4.7 stars, $12").
- Reading order follows visual order.
- Announce results of actions that don't move focus ("Added 250 ml. 1.5 litres today").
- Decorative images are hidden from screen readers; meaningful images get a description.
- Custom controls (sliders, steppers, toggles) expose their role, value and how to adjust them.

## Motion and touch

- Respect reduced-motion settings: swap movement, parallax and auto-playing animation for fades or instant changes.
- No essential information only in an animation or only on hover/long-press.
- Touch targets ≥44pt / 48dp with spacing between them.
- Every gesture has a visible alternative (swipe-to-delete also has an edit/delete button).
- No time limits that can't be extended.

## Dark mode

Not an inverted light theme.

- Background near-black (around #0B0B0C–#121212), not pure #000 everywhere; pure black only as a deliberate choice for OLED-style looks.
- Show elevation with lighter surfaces, not shadows: background < surface < elevated surface.
- Text is off-white (~87% white for primary, ~60% for secondary), not pure white on black.
- Desaturate and lighten the accent so it doesn't vibrate on dark backgrounds; recheck contrast.
- Photos and illustrations may need a slight dim; logos and mascots may need a dark variant.
- Separators get lighter, not darker.
- Follow the system setting by default; an in-app override is optional.
- Check every screen, state, chart and widget in both modes.
