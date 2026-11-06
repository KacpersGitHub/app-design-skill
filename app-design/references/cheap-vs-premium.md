# Cheap vs premium

## The 12 details users feel

Each is small; together they decide whether an app feels cheap.

| # | Cheap | Premium |
|---|-------|---------|
| 1 | No legal line on sign-up/data entry | "By continuing you agree to our Terms and Privacy Policy" above the CTA — signals someone is behind it |
| 2 | Empty state or dead end with nowhere to go | Every empty state has an exit or next action |
| 3 | Ambiguous actions ("where does this note show up?") | One line of helper text under the field/action |
| 4 | Action completes silently | Success state: check animation + haptic, toast, or confirmation screen |
| 5 | "Something went wrong" | Specific, prescriptive errors ("Password needs 8+ characters") |
| 6 | Bare spinner | Skeletons, progress text that says what's happening ("Analyzing your week…") — known waits feel shorter |
| 7 | Asks for info it already has | Remember and prefill; never ask twice |
| 8 | Mixed icons (stroke widths, filled + outline, random tinted backgrounds) | One icon family, one stroke weight, one fill style |
| 9 | Cute/vague labels ("Let's go!", "Add") | Literal labels ("Confirm purchase", "Add to cart") |
| 10 | Permission wall at launch, before any value | Ask in context, right before the feature that needs it |
| 11 | Filters must be unchecked one by one | "Clear all" always available |
| 12 | Decision-critical info truncated or hidden | Never hide what the user needs to decide |

## Signs an app looks AI-generated

- Purple/blue gradients, glowing blobs, glassy cards on everything.
- Every section a card inside a card; every card the same size.
- Tinted circle behind every icon, each a different color.
- Emoji used as icons; sparkle icons for "AI".
- Generic hero copy ("Unlock your potential", "Elevate your journey").
- Everything centered, everything bold, many font sizes.
- Stats and badges no one asked for.

Fix: pick one accent, drop decoration, let real content (photos, numbers, the user's own data) be the visual, and give the app one distinctive element (a mascot, an illustration style, a signature animation) instead of ten generic ones.

## Visual craft

- **Design for the system, not one screen.** Content varies (bright/dark/busy images, long names, missing data). Icons over images get a subtle background container so they read on any photo. Put names and numbers *below* user photos, not on them, so cards look consistent whatever is uploaded.
- **Imagery consistency.** Same background, lighting and framing across a catalog. Clear focal point on the thing itself — not hands or props. A beautiful image that breaks the set is the wrong image.
- **Grid & alignment.** One screen margin everything snaps to. Misalignment is felt even when not seen.
- **Shape language.** One radius scale (tokens.md).
- **Color.** Muted, mood-appropriate palette that supports content. Too many saturated colors = no hierarchy.
- **Typography.** One family; hierarchy from size, weight, color, line-height. Headlines attract, paragraphs support: body gets generous line-height and slightly softer color (still ≥4.5:1). Small uppercase labels get a little letter-spacing.
- **Hierarchy test.** If you can't say which element is read first, neither can the user. The title steps up; the key stat (rating, price, progress) gets weight; everything else steps back.
- **Badges** scan instantly: "20% off", not "20% off discount 🏷".
- **Dividers** hairline or replaced by spacing. **Spacing** shows relationships — too much disconnects as badly as too little.
- **Remove redundant labels** ("Price:" before "$4.99"). If you label one control, label its sibling.
- **Titles describe the thing**, not a variable (no "1 kg" in the title when quantity is selectable).
- **Information order = decision order.** What is it → can I trust it → what does it cost → act.
- **Primary CTA** is the most important element but refined, not shouting (no all-caps giant). Related controls sit together (quantity next to Add). Put the outcome in the button: "Add to cart · $8.40", "Show 41 homes".
- **Above the fold is not the goal.** Everyone scrolls. The first thing seen must be worth continuing for.

## Microcopy

- **Buttons:** verb + object ("Save workout", "Start 7-day trial"). Not "OK", "Submit", "Let's go".
- **Errors:** what happened + how to fix, no blame ("That code expired. Send a new one").
- **Empty states:** what goes here + one action ("No workouts yet. Log your first one").
- **Permission pre-prompts:** the benefit in one line, then the system dialog ("Get a reminder when it's time to drink").
- **Success:** past tense, specific ("Workout saved", "Added 250 ml").
- **Destructive actions:** name the consequence ("Delete 3 photos? This can't be undone"), destructive button in the error color, safe option easiest to hit.
- Same word for the same thing everywhere ("workout" never becomes "session" on another screen).
