# app-design — Claude Code skill

A mobile app design playbook for Claude Code: what makes an app feel premium vs cheap, visual craft, junior→staff design thinking, UX psychology, filter/list/product-page patterns, motion strategy, iOS Live Activities / Dynamic Island / widgets, and a reference-first AI build workflow.

Distilled from videos by Wyatt Feaster, uxpeak, and Jason Lee.

## Install

Copy the `app-design` folder into your Claude Code skills directory:

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

Start a new Claude Code session. The skill loads automatically when you design or review app screens, or call it with `/app-design`.
