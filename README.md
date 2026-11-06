# app-design — Claude Code skill

Teaches Claude what makes a mobile app feel premium instead of cheap, and what it should add to every app. Framework- and tool-agnostic: it's about design decisions, so it works whatever the app is built with.

**What's inside**

- `SKILL.md` — the core: restraint rules, "what every app needs" checklist, how to review an app, final audit
- `references/tokens.md` — concrete values: spacing scale, type sizes (iOS + Material), touch targets, contrast, radius, motion timing
- `references/cheap-vs-premium.md` — the 12 details users feel, signs of an AI-generated look, visual craft, microcopy
- `references/patterns.md` — junior → staff decisions for lists, filters, detail pages, search, forms; per-screen checklists
- `references/psychology.md` — smart defaults, goal gradient, reciprocity, IKEA effect, loss aversion (with guardrails), anchoring
- `references/motion-haptics.md` — what motion is for, must-have animations, characters/mascots, haptic mapping, sound
- `references/platforms.md` — iOS vs Android conventions, widgets, live activities, ongoing notifications
- `references/accessibility.md` — text scaling, contrast, screen readers, reduced motion, dark mode

Claude reads `SKILL.md` and only opens the reference files a task needs.

## Install

```bash
git clone https://github.com/KacpersGitHub/app-design-skill.git
mkdir -p ~/.claude/skills
cp -r app-design-skill/app-design ~/.claude/skills/
```

On Windows (PowerShell):

```powershell
git clone https://github.com/KacpersGitHub/app-design-skill.git
New-Item -ItemType Directory -Force "$HOME\.claude\skills" | Out-Null
Copy-Item -Recurse app-design-skill\app-design "$HOME\.claude\skills\"
```

Start a new Claude Code session. The skill loads automatically when you design, review or improve app screens, or call it with `/app-design`.

## Update

```bash
cd app-design-skill && git pull
```

Then copy the `app-design` folder over your installed copy again.

## Sources

Wyatt Feaster, uxpeak and Jason Lee (YouTube), Apple Human Interface Guidelines, Material Design 3, WCAG 2.2.
