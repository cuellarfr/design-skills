# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

A collection of 10 UX/design skills for AI coding agents (Claude Code, Cursor, Codex, and others). Each skill is a set of markdown files that give AI tools deep knowledge of established design frameworks, heuristics, and methodologies. There is no build system, no tests, and no application code — this is a pure content repository.

Skills are installed into agents via `npx skills add cuellarfr/design-skills`.

## Skill Architecture

Every skill follows the same structure:

```
skill-name/
├── SKILL.md              # Main file (200-350 lines), standalone
├── references/            # Deep reference material, loaded on demand
├── templates/             # Fillable deliverable templates
└── examples/              # End-to-end walkthroughs and scenarios
```

SKILL.md files use YAML frontmatter with `name` and `description` fields. The description is what agents use to decide when to load the skill.

## The 10 Skills

`ux-research`, `design-critique`, `accessibility-audit`, `journey-mapping`, `design-systems`, `ux-strategy`, `interaction-design`, `design-ops`, `ux-writing`, `design-elevation`

## Content Conventions

- **Opinionated defaults** — Specific numbers, benchmarks, and rubrics; not "consider..." language
- **Actionable over theoretical** — Every principle includes a concrete recommendation
- **Before/after examples** — Show what bad and good look like, with scoring
- **Progressive depth** — SKILL.md is comprehensive standalone; reference files go deeper
- **Grounded in sources** — Built from established books and frameworks, not invented heuristics

## Other Files

- `index.html` — GitHub Pages landing page (single-file, self-contained HTML/CSS/JS with dark mode support)
- `README.md` — Full skill descriptions and installation instructions
- `LICENSE` — MIT
