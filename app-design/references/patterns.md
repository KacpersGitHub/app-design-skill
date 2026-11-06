# Patterns: junior → staff, and per-screen checklists

Use the ladder to push a screen one level up. Then apply restraint: keep a higher-level addition only if it changes what the user decides. Making the interface *look* simpler is not the same as making the decision easier — design for the decision, then cut what doesn't serve it.

## Lists and feeds

- **Junior:** tiny thumbnails to fit more above the fold; filters buried in dropdowns; flat small text with no hierarchy; mixed shapes.
- **Mid:** big image as the hero of each card; one radius; clear hierarchy (name up, rating weighted, rest back); quick-filter chips visible.
- **Senior:** full-width imagery; custom icon set for categories (personality, and it doesn't compete with content photos); chips + Filters + Sort; result count ("640 places"); layout toggle (cards vs compact list) only when no single default fits.
- **Staff:** search placeholder says what's searchable ("places, dishes, cuisines"); quieter supporting UI so content stands out; personalized label ("Best match"); text below the photo for consistency.

## Filters

The job: help users narrow down while they're still figuring out what they want.

- **Junior:** one page per filter → many taps, related choices never visible together, results disappear, button gives no feedback.
- **Mid:** bottom sheet over the results; everything in one scroll; slider + exact inputs for ranges; button shows the live count ("Show 41 homes"). Steppers (+/−) only for nudging an existing value like cart quantity — not for picking a known value.
- **Senior:** histogram behind the range slider; all options visible at once as segments ("1+ 2+ 3+ 4+", where "3+" means at least 3); icons on type options.
- **Staff:** context around the control ("459 of 1,557 fit"); translate what the user actually knows into the filter (deposit + monthly budget → max price, drawn on the histogram); result count on each option before tapping; ranges by tapping two values. Every added number must help a trade-off, otherwise it's noise.

## Detail and product pages

- Order: what it is → rating next to the title → price early → options → action.
- Hero image under a content sheet that slides up on scroll; the title moves into the top bar so context is never lost.
- Sticky bottom bar with quantity/options and the main button, total included.
- Quick-pick presets from real usage (500 g / 1 kg / 2 kg) plus a custom option.

## Search

- Show recent and suggested searches before typing.
- Results update as you type; typo-tolerant.
- No-results state suggests a broader query or removing a filter.

## Forms

- Prefill everything known; smart defaults for the rest.
- Right keyboard per field (email, number, phone); autofill hints; next/done moves through fields.
- Validate inline after the user leaves a field, not on every keystroke.
- Errors next to the field, saying how to fix.
- Long forms split into short steps with visible progress.

## Per-screen checklists

- **Onboarding:** value before asking · let users try the core action · progress never at zero · smart defaults · permissions in context · legal line on data entry · button says "Continue".
- **Sign-up / login:** social/passkey options first if offered · one field per concept · show-password toggle · clear path to "forgot password".
- **Paywall:** real stakes only · anchor the price (yearly shown per week or month vs monthly) · plain plan labels · trial terms in plain words · visible close and restore purchases.
- **Home / tracker:** one hero metric · one obvious primary action · animated state change + haptic · success feedback · clear "what to do next".
- **Lists:** big imagery · hierarchy · chips + filter + sort · result count · layout toggle only if needed.
- **Filters:** sheet over results · one scroll · histogram ranges · "N+" segments · live count in button · Clear all.
- **Empty / error / loading / offline:** exit route · prescriptive errors · skeletons + descriptive progress text · what still works offline.
- **Settings:** grouped with plain labels · notifications · account and privacy (including delete account) · support/feedback · restore purchases · app version · feature toggles with a one-line description.
