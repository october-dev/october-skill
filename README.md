# October Themes Skill

A skill (slash command) that injects curated design system themes into your AI coding session. Works with Claude Code, OpenCode, Gemini CLI, Codex CLI, and any tool that supports the [Agent Skills](https://agentskills.io) standard.

**One command to make all AI-generated UI in your session look polished instead of generic.**

No API key needed. Completely free.

## Install

**Option A — Personal (all projects):**

```bash
mkdir -p ~/.claude/skills/inject-theme
curl -o ~/.claude/skills/inject-theme/SKILL.md \
  https://raw.githubusercontent.com/october-dev/october-skill/main/.claude/skills/inject-theme/SKILL.md
```

**Option B — Per project:**

```bash
mkdir -p .claude/skills/inject-theme
curl -o .claude/skills/inject-theme/SKILL.md \
  https://raw.githubusercontent.com/october-dev/october-skill/main/.claude/skills/inject-theme/SKILL.md
```

## Use

```
/inject-theme desktop-web
/inject-theme mobile-app
/inject-theme game
/inject-theme
```

The AI will fetch a curated design theme and apply it to all UI code generated in the session.

## What It Does

1. Fetches a weighted-random theme from October's library of 1000+ curated design systems
2. Shows you the theme name and aesthetic summary
3. Asks for confirmation (or pick a different one)
4. Applies the full design system to all UI code for the rest of the session

Each theme includes: color palette, typography, component styles (real Tailwind classes), effects, animations, and Non-Genericness Rules that prevent bland output.

## Platforms

- `desktop-web` — Websites, dashboards, SaaS apps
- `mobile-app` — iOS/Android apps
- `game` — Browser games

Omit the platform argument to get a theme for any platform.

## License

MIT

---

Built by [October](https://october.dev) — the AI-native canvas for building apps.
