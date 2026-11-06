# Design tokens: concrete values

Use these as defaults. If the app already has a design system, follow it and only fill gaps. What matters most is that every value comes from one scale.

## Spacing

- **Base unit 4.** Scale: 4, 8, 12, 16, 24, 32, 48, 64.
- **Screen margin:** 16–20pt on phones (pick one and use it everywhere). 24 on larger phones/tablets if content is sparse.
- **Inside components:** 8–16. **Between related items:** 8–12. **Between groups/sections:** 24–32. **Before a new major section:** 48.
- Rule: space *inside* a group is smaller than space *between* groups. That's how users see what belongs together.
- Card padding 16; list row vertical padding 12–16; minimum row height 44pt / 48dp.

## Touch targets

- **Minimum 44×44pt (iOS), 48×48dp (Android)**, even if the visible icon is smaller — extend the hit area.
- At least 8 between adjacent targets.
- Primary buttons: 48–56 tall, full width or clearly dominant. Bottom-of-screen actions sit in the thumb zone.

## Typography

One family (the system font is a safe default: SF Pro on iOS, Roboto/Google Sans on Android). Build hierarchy with size and weight, not more fonts.

**iOS default sizes (pt):** Large Title 34 · Title 1 28 · Title 2 22 · Title 3 20 · Headline 17 semibold · Body 17 · Callout 16 · Subheadline 15 · Footnote 13 · Caption 12 / 11.

**Material 3 sizes (sp):** Display 57/45/36 · Headline 32/28/24 · Title 22/16/14 · Body 16/14/12 · Label 14/12/11.

- Use 3–4 sizes per screen, not 8.
- **Body text never below 15pt/14sp**; captions never below 11.
- Line height: ~1.2–1.3× for headings, ~1.4–1.5× for body.
- Weights: regular for body, semibold for emphasis and titles. Avoid bold-everything.
- Numbers that change (timers, counters, prices in lists) use tabular figures so they don't jitter.
- Line length for reading text: 45–75 characters.

## Corner radius

- One scale, for example: 8 (small: chips, inputs), 12–16 (cards, buttons), 24+ (sheets, large cards), full (pills, avatars).
- **Nested shapes:** inner radius = outer radius − padding, so corners stay parallel.
- Don't mix sharp and very round shapes on one screen without a reason.

## Color

- **Roles, not colors:** background, surface, elevated surface, primary text, secondary text, tertiary/disabled text, separator, accent, success, warning, error.
- **One accent.** Accent marks the primary action and selection, nothing decorative.
- Neutrals carry 90% of the screen. Tint grays slightly toward the brand hue so they don't look dead.
- Text contrast **≥4.5:1** (≥3:1 for text 18pt+ or 14pt bold, and for icons/borders that convey meaning).
- Secondary text is a lighter tone of the same neutral, not a different hue.
- Status colors are always paired with an icon or text — color alone never carries meaning.
- Dark mode values: see [accessibility.md](accessibility.md).

## Elevation & separation

- Prefer spacing and subtle surface tone changes over borders and heavy shadows.
- Separators: hairline, low contrast, or none.
- Shadows: soft, large blur, low opacity; one or two levels only (resting, floating).

## Icons

- One family, one stroke weight, one style (outline *or* filled — filled usually reserved for the selected state).
- Common sizes: 16, 20, 24. Optically align with text baseline/cap height.

## Motion timing

| Kind | Duration |
|------|----------|
| Press feedback, toggles, small state | 100–150 ms |
| Small element moves, fades, chips | 150–250 ms |
| Sheets, cards, page-level transitions | 250–400 ms |
| Large, expressive, celebratory | 400–600 ms |

- Exits ~20–30% faster than entrances.
- Ease out for things entering, ease in for things leaving, ease in-out for things moving on screen. Never linear except for continuous loops/progress.
- Prefer springs for anything the user touches or drags: critically damped (no bounce) for most UI; a little bounce only for playful, celebratory moments.
- Stagger lists by 20–40 ms per item, capped at ~5–6 items.
