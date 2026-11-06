---
name: app-design
description: What makes a mobile app feel premium instead of cheap, and what Claude should add to every app. Covers the details users notice (feedback, success/empty/error/loading states, copy, icons), concrete design values (spacing, type scale, touch targets, contrast, motion timing), visual hierarchy and restraint, junior→staff design decisions for lists, filters and detail pages, UX psychology for onboarding and paywalls (smart defaults, progress, value before sign-up, anchoring), motion and haptics, accessibility and dark mode, and home-screen widgets, live activities and notifications on iOS and Android. Use when designing, reviewing or improving any app screen or flow, when an app "feels cheap", "looks AI-generated", "feels crowded" or "needs polish", or when deciding what an app is missing.
---

# App Design

**Core idea:** cheap apps leave doubt; premium apps remove it. A good app always tells the user what is happening, what will happen next, and what they control — with as little on screen as possible.

This skill is about design decisions, not any framework or tool. Apply it whatever the app is built with.

## How to use this skill

- **Designing or building a screen:** start from "What every app needs" and "Restraint" below, take values from [tokens](references/tokens.md), then open the reference for the screen type.
- **Reviewing or improving an existing app:** go through the final audit and [cheap vs premium](references/cheap-vs-premium.md). Report findings as a table: *problem → why it hurts the user → fix*, most damaging first. Then add what's missing from "What every app needs".
- Open only the references the task needs:

| Task | Reference |
|------|-----------|
| Any new screen; spacing, type, color, sizes | [tokens.md](references/tokens.md) |
| Polish pass, "feels cheap", copy and labels | [cheap-vs-premium.md](references/cheap-vs-premium.md) |
| Lists, feeds, search, filters, detail/product pages, per-screen checklists | [patterns.md](references/patterns.md) |
| Onboarding, sign-up, paywall, upsell, pricing | [psychology.md](references/psychology.md) |
| Animation, transitions, characters/mascots, haptics, sound | [motion-haptics.md](references/motion-haptics.md) |
| iOS vs Android conventions; widgets, live activities, notifications | [platforms.md](references/platforms.md) |
| Font scaling, screen readers, contrast, dark mode, reduced motion | [accessibility.md](references/accessibility.md) |

## Restraint comes first

Premium is mostly subtraction.

- **One job per screen, one primary action.** Secondary actions are visibly quieter.
- **Information earns its place only if it changes a decision.** A count, badge, chart or helper line that doesn't change what the user does next gets cut.
- **One accent color**, used for the primary action and real state (selected, success, error).
- **Short, literal copy.** Cut it in half, then check again.
- **One spacing rhythm** from the token scale. No eyeballed gaps.
- **Fewer, bigger things beat many small things.** If a screen feels crowded, remove elements before shrinking them.

## What every app needs

Add these when they're missing. They are what separates a finished app from a demo.

**Feedback on everything**
- Pressed state on every tappable element (scale/opacity change, plus a light haptic on key actions).
- A success state after every meaningful action: check animation, toast, or confirmation screen, with a success haptic.
- Specific, fixable error messages next to the thing that failed.
- Loading that explains itself: skeletons shaped like the content, or progress text saying what's happening. A bare spinner only for waits under ~1 second.

**No dead ends**
- Empty states that explain what goes there and offer one action to fill it.
- A way back or out from every screen; system back/swipe-back always works.
- "Clear all" on filters; undo for destructive or easy-to-mistake actions (better than "Are you sure?").
- Offline and no-permission states that say what still works and how to fix it.

**Trust**
- Legal line above sign-up/data-entry CTAs ("By continuing you agree to the Terms and Privacy Policy").
- Permissions asked in context, right before the feature that needs them, with a one-line benefit first.
- Never ask for information the app already has. Prefill and remember.
- Clear, honest pricing and trial terms; visible restore and close on paywalls.

**First-run experience**
- Value before sign-up: let users try the core action or see a real result first.
- Smart defaults on every choice; progress that never starts at zero.
- Short onboarding that sets up the user's goal, not a feature tour.

**Feel**
- Motion that explains state changes (where things come from and go to), never decoration for its own sake.
- Haptics on the moments that matter (toggle, snap, success, error).
- Dark mode and large font sizes that actually work.
- One icon family, one corner-radius scale, one type family.

**Coming back**
- Something worth returning to: progress, streak, history, or a reminder the user chose.
- A home-screen widget or live activity if the app tracks something over time.
- A settings screen with notification controls, account, privacy, support/feedback and restore purchases.

## Final audit

- [ ] One primary action? Is the first thing the eye reads the right thing?
- [ ] Could one more element or line of copy go without losing a decision input?
- [ ] Spacing, type, radius and color all from one scale? One icon style?
- [ ] Works with worst-case content: bright image, long name, no data, largest font size, dark mode?
- [ ] Every action has feedback; every wait says what's happening; every error says how to fix it?
- [ ] No dead ends; filters resettable; nothing decision-critical truncated; back always works?
- [ ] Defaults prefilled; nothing asked twice; permissions asked in context?
- [ ] Buttons say exactly what happens (with the outcome, price or count where useful)?
- [ ] Touch targets ≥44pt (iOS) / 48dp (Android); text contrast ≥4.5:1; icon-only buttons labelled for screen readers?
- [ ] Motion explains state and respects reduced-motion settings?
- [ ] Psychology used to remove friction, never to trick?

---

Sources: Wyatt Feaster "12 Mistakes That Make Your App Feel Cheap"; uxpeak "This UI/UX Redesign Will Teach You More Than 100 Tutorials", "The UX Psychology Behind Apps People Can't Stop Using", "Bad vs Great UX/UI Design"; Jason Lee's animated-app videos; Apple Human Interface Guidelines; Material Design 3; WCAG 2.2.
