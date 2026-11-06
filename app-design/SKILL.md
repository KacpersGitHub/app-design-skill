---
name: app-design
description: End-to-end mobile app design playbook — what makes an app feel premium vs cheap, visual craft (grid, type, color, icons, spacing), junior→staff design thinking, UX psychology (defaults, goal gradient, reciprocity, IKEA effect, loss aversion, anchoring), filter/list/product-page patterns, motion and character animation strategy, Dynamic Island / Live Activities / widgets, and the reference-first AI build workflow. Use when designing, building, reviewing or redesigning any app screen or flow (onboarding, paywall, home, list, filters, product page, settings, empty/error/loading states), when an app "feels cheap", "looks AI-generated", or needs to feel premium, or when planning animations, widgets or a landing page for an app.
---

# App Design

Distilled from six videos: Wyatt Feaster "12 Mistakes That Make Your App Feel Cheap"; uxpeak "This UI/UX Redesign Will Teach You More Than 100 Tutorials", "The UX Psychology Behind Apps People Can't Stop Using", "Bad vs Great UX/UI Design"; Jason Lee "Opus 5.5 for Dynamic Island animations" and "Vibe Code an Animated App".

**Core thesis:** cheap apps leave doubt; premium apps remove it. Every rule below is a way of telling the user what is happening, what will happen, and what they control.

Related skills: `animate-expo` / `expo-animation` (implement motion), `apple-design` (fluid physical motion), `copywriting` (landing/CTA copy), `expo-overview` (build/ship).

---

## 1. Workflow (do in this order)

1. **References first, never design blind.**
   - Real shipped flows: Mobbin (use Mobbin MCP if connected — search the pattern, e.g. "onboarding", "filters", "paywall", and compare how leading apps solve it). Note what they share and where they diverge.
   - Motion references: screen recordings of the real app you're learning from (screenshots don't show animation). Watch them for page flow + how each element animates.
   - Mood/style: Pinterest-type image references for one-off visuals (a pool look, a Dynamic Island style).
   - Platform rules: read the official guidelines (Apple HIG for Live Activities/widgets — sizes, padding, compact/minimal/expanded, animation durations). Find them yourself; don't wait for a URL.
2. **Prototype on localhost inside a real phone mockup** with **preview controls** (e.g. "add drink", "reset", "simulate") so animations and states can be triggered on demand. Offer **2–3 variations** when direction is open.
3. **Build ~95% structure first** (all screens, flow, logic, simple animations), then polish the hard 5% (characters, signature moments).
4. **Iterate from screen recordings with voice-over** when the user gives feedback that way — the cursor shows what they mean. Batch fixes.
5. **Port to the real stack** (React Native/Expo; Swift only for widget/Live Activity extensions). Test on device.
6. **Landing page last** — once the app exists it can reuse real screens, animations, colors. Write copy for benefits, not features (see §9).

---

## 2. Premium vs cheap: the 12 detail checks

Run this on every flow. Each is small; together they decide "feels cheap".

| # | Cheap | Premium |
|---|-------|---------|
| 1 | No legal line on sign-up/data entry | "By continuing you agree to our Terms and Privacy Policy" above the CTA — signals someone is behind it |
| 2 | Empty state / dead end with nowhere to go | Every empty state has an exit or next action |
| 3 | Ambiguous actions ("where does this note show up?") | One line of helper text under the field/action |
| 4 | Action completes silently | Success state: toast, check animation, or confirmation screen |
| 5 | "Something went wrong" | Specific, prescriptive errors ("Password needs 8+ characters") |
| 6 | Bare spinner | Skeleton loaders, progress text that says what's happening ("Analyzing your week…"), purposeful animation — known waits feel shorter |
| 7 | Asks for info it already has | Remember and prefill; never ask twice |
| 8 | Mixed icons (stroke widths, filled+outline, random colored tinted backgrounds) | One icon family, one stroke weight, one fill style, color used intentionally |
| 9 | Cute/vague labels ("Let's go!", "Add") | Literal labels ("Confirm purchase", "Add to cart") |
| 10 | Permission wall at launch (location, notifications) before value | Ask in context, right before the feature that needs it, after value shown |
| 11 | Filters must be unchecked one by one | "Clear all" always available |
| 12 | Decision-critical info truncated/hidden | Never hide what the user needs to decide |

---

## 3. Visual craft (screen-level polish)

- **Design for the system, not one screen.** Content changes (bright/dark/busy images, long names). Icons over images get a subtle background container + contrast/outline so they work on any photo. Put names and numbers *below* user-uploaded photos, not on them, so cards look consistent whatever is uploaded.
- **Imagery consistency.** Product/content images share background, lighting, framing. A clear focal point on the thing being sold/tracked — not hands, not props, not a single item when sold by weight. A beautiful image that breaks the grid is the wrong image.
- **Grid & alignment.** One left margin (e.g. 24px / 16–24pt) everything snaps to. Misalignment is felt even when not seen.
- **Shape language.** One corner-radius scale used everywhere. Don't mix 4px corners with circles on the same screen.
- **Color.** Muted, mood-appropriate palette that supports content. Too many saturated colors = weak hierarchy. Color only where it means something.
- **Typography.** One family is enough; build hierarchy with size, weight, color, line-height. Headlines attract, paragraphs support: body gets generous line-height and slightly reduced contrast. Small uppercase labels get letter-spacing.
- **Hierarchy test.** If you can't say which element is read first, neither can the user. Title steps up; key stat (rating, price) gets weight; everything else steps back. Scanning beats reading.
- **Badges** are instantly scannable: "20% off", not "20% off discount 🏷".
- **Dividers** soft and light, never heavy black blocks. **Spacing** expresses relationships — too much space disconnects as badly as too little.
- **Remove redundant labels** ("Price:" before "$4.99"). Be consistent: if you label one control, label its sibling.
- **Titles describe the thing**, not a variable (no "1 kg" in title when quantity is selectable).
- **Information order = decision order.** What is it → can I trust it (rating next to title) → what does it cost (price early) → act.
- **Primary CTA** is the most important element but refined, not shouting (no all-caps giant). Put related controls together (quantity next to Add). Put the outcome in the button: "Add to cart · $8.40", "Show 41 homes", "See 12 results".
- **Above-the-fold is not the goal.** Everyone scrolls. The first thing seen must be worth continuing for — bigger, appetizing imagery beats cramming six tiny rows.

### Structural upgrades after fixing mistakes
- Content as a rounded scrollable card sliding over a hero image; title collapses into a sticky nav so context is never lost.
- Sticky bottom action bar (quantity + CTA) — users decide to act after scrolling.
- Preset quick-picks from real usage (500g / 1kg / 2kg) plus custom input for flexibility.

---

## 4. Junior → Staff: how decisions level up

Use this ladder to push any screen one level higher.

**Lists/feeds**
- Junior: tiny thumbnails to fit more above fold; filters buried in dropdowns; flat 11–13px text, no hierarchy; mixed shapes.
- Mid: big image as hero of card; consistent radius; clear hierarchy; quick-filter chips visible.
- Senior: full-width imagery; custom icon set for categories (personality + doesn't compete with content photos); chips + "Filters" + "Sort" buttons; result count ("640 places"); layout toggle (cards vs compact list) when no single default fits everyone.
- Staff: search placeholder says what's searchable ("places, dishes, cuisines"); quieter supporting UI so content stands out; personalized label ("Best match"); text off the photo for consistency.

**Filters** (the job is to help users narrow while they're still figuring out what they want)
- Junior: one page per filter → many taps, can't see related choices together, results vanish, CTA gives no feedback.
- Mid: bottom sheet over results; everything in one scroll; slider + manual inputs for ranges; CTA shows live count ("Show 41 homes"). Don't use steppers for picking a known value — steppers are for nudging (cart qty, thermostat).
- Senior: histogram behind range slider (see where the market is); segmented "1+ 2+ 3+ 4+" options visible at once ("3+" = at least, matching how people think); icons on type options.
- Staff: context around the control ("459 of 1,557 fit"); translate the user's real inputs into the filter (deposit + monthly payment → max price, drawn on the histogram); show per-option result counts before selecting; allow ranges by tapping two values. Trade-off: every added datum must help the decision, not add noise.

**Rule:** making the interface look simpler ≠ making the decision easier. Optimize for the decision.

---

## 5. UX psychology (use honestly)

1. **Smart defaults** — prefill every field with the most common choice. 70–90% never change defaults; a default reads as a recommendation. User's job becomes "scan and adjust". Fewer choices convert better (jam study: 24 options → 3%, 6 → 30%).
2. **Goal gradient / never start at zero** — frame account creation as step 1 and show progress already at ~20%. Count something the user already did. Momentum beats a blank 0%.
3. **Reciprocity** — give value before asking. Show a real, useful partial result, *then* "Save your full report". Never blur results behind a sign-up wall.
4. **IKEA / endowment effect** — let users build something before sign-up (name, goal, color, first lesson, first log). CTA says "Continue", not "Sign up" — leaving now means abandoning something theirs. (Duolingo: language, goal, first lesson before account.)
5. **Loss aversion** — losses weigh ~2× gains. Frame upgrades around what the user would actually lose (their real items, by name), not abstract gains. **Guardrail:** only real stakes and real deadlines; no fake countdowns or shaming dismiss copy — that erodes the trust everything else here builds. Keep a plain, respectful decline option.
6. **Contrast / anchoring** — never show a cost in isolation. Show add-ons next to the main item ("$50 · just 2.6%"), lead with the anchor. Control what the user sees first; it becomes the ruler.

---

## 6. Motion & animation

**Every state change gets motion that explains it:** success confirmations, water/progress rising when logged, skeletons while loading, sheets sliding from their source, sticky headers morphing.

**Two kinds of animation — build them differently:**
- **Interface motion → code.** Sliders, liquid levels, bubbles, progress, toggles, chips, ripples. Interactive, tiny, crisp at any size. Always prefer code here.
- **Character / organic motion → not hand-coded rigs.** Code-animated characters look like puppets on sticks. Options:
  - Static or gently floating character → **SVG** (vector, sharp at any scale, tiny file) + code-driven transforms.
  - Real movement (jump, swim, sip) → generated **video** (image-to-video / motion-transfer from a reference clip), on green screen for keying, compressed/upscaled small. Cheaper motion-transfer models are often good enough — don't default to the priciest.
  - Or Lottie/Rive if the team can author it.

**Delight patterns that earn their place:**
- Idle wiggle on unselected options to invite the first tap (onboarding choices).
- Sensor-driven scenes: character follows device tilt (gyroscope/gravity) and touch, with water ripples — great as a first-open "this app is alive" moment.
- Interactive onboarding: let users try the core action (add water, move slider) before signing up — doubles as the IKEA effect.
- Swipeable rows for overflowing options (verify swipe actually works).
- Sound effects on key actions, subtle and optional.

Motion quality bar: smooth, interruptible, spring-based; respect Reduce Motion. Implementation: `animate-expo` skill.

---

## 7. Live Activities, Dynamic Island, widgets (iOS)

- Use for things the user tracks while outside the app (timers, progress, countdown to next action). Must stay useful when the app is backgrounded.
- Design all three Island presentations: **minimal, compact, expanded**, plus **Lock Screen** Live Activity and a **home-screen widget** (square). Follow HIG sizes/padding/fonts/animation timing.
- Reuse the app's design language (brand color, mascot/object, e.g. a glass filling) — the expanded view can show streak, countdown, and one action button.
- Widget buttons can perform the action directly (App Intents) — no need to open the app.
- Add a **Settings toggle** to enable/disable Live Activity, with a preview of what it looks like and a one-line description.
- Prototype in browser with simulate/reset controls first, then implement in Swift widget extension. Expo Go can't test this — needs a **development build** (EAS) + paid Apple developer account.

---

## 8. Screen-by-screen checklist

**Onboarding:** value before ask · interactive first action · progress never at 0 · smart defaults · permissions asked in context · legal line on data entry · CTA "Continue".
**Paywall:** real loss framing only · anchor the price (yearly vs monthly per-week) · clear plan labels · clear restore/close.
**Home/tracker:** one hero metric, obvious primary action, state change animated, success feedback.
**Lists:** big imagery, clear hierarchy, chips + filter + sort, result count, layout toggle if needed.
**Filters:** sheet over results, all in one scroll, histogram ranges, "N+" segments, per-option counts, live count in CTA, Clear all.
**Detail/product:** decision order (what → trust → cost → act), sticky CTA with total, presets.
**Forms:** prefilled, helper text, specific errors, never re-ask.
**Empty/error/loading:** exit route, prescriptive errors, skeletons + descriptive progress text.
**Settings:** feature toggles with preview + description.

---

## 9. App landing page

Build after the app. Reuse real app animations, widgets, Dynamic Island demos, mascot. Then a copy pass with the `copywriting` skill: benefits not features, short and punchy, written for the user; add social proof (store rating, reviews) and an FAQ. Always human-review final wording.

---

## 10. Final audit (run before calling a screen done)

- [ ] Can I name the first thing the eye reads? Is it the right thing?
- [ ] Every element on one grid, one radius scale, one icon style, one type family?
- [ ] Works with the worst-case content (bright image, long name, empty data)?
- [ ] Every action has feedback; every wait says what's happening; every error says how to fix it?
- [ ] No dead ends; filters resettable; nothing decision-critical truncated?
- [ ] Defaults prefilled; nothing asked twice; permissions in context?
- [ ] Buttons say exactly what happens (and the outcome/price/count)?
- [ ] Psychology used to reduce friction, not to trick?
- [ ] Motion explains state, is smooth, respects Reduce Motion; characters not puppet-rigged?
