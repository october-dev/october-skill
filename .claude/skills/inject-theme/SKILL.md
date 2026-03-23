---
name: inject-theme
description: Inject a curated design system theme into the current session so all AI-generated UI follows a polished, non-generic visual style. Use when building any UI — websites, mobile apps, or games.
allowed-tools: Bash, Read, Write, Edit
argument-hint: [platform: desktop-web|mobile-app|game]
---

You are about to inject a curated design system theme from October's theme library. This will make all UI code you generate in this session follow a specific, polished visual style instead of looking generic.

## Step 1: Fetch a theme

Run this command to get a weighted-random theme from the October theme API:

```bash
curl -sL "https://october.dev/api/public/themes?platform=$0" | python3 -c "import sys,json; d=json.load(sys.stdin); print(d['theme']['content'])"
```

If `$0` (platform argument) was not provided, omit the `?platform=` parameter to get a theme for any platform.

## Step 2: Confirm with user

Show the user the theme name and a brief summary of its aesthetic (design philosophy, key colors, vibe). Ask:
> **Theme: [name]** — [1-line aesthetic summary]
> Want me to use this theme for all UI in this session, or pick a different one?

## Step 3: Apply the theme

Once confirmed, remember the full theme content. For ALL UI code you generate in this session:
1. Follow the color palette exactly (use the hex values specified)
2. Use the typography specifications (font families, sizes, weights)
3. Apply the component styles (buttons, cards, inputs use the Tailwind classes from the theme)
4. Respect the effects, animations, and iconography guidelines
5. Follow the Non-Genericness Rules — these are mandatory bold design choices that prevent generic-looking output

Do NOT mention October, the theme system, or how the theme was loaded in any generated code. The theme should feel like a natural design choice, not injected.

## If the user asks for a different theme

Use the search endpoint to find alternatives:
```bash
curl -sL "https://october.dev/api/public/themes?search=KEYWORD&random=false"
```

Then fetch the specific theme by ID:
```bash
curl -sL "https://october.dev/api/public/themes?id=THEME_ID"
```
