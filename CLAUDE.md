# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

A collection of 10 UX/design skills for AI coding agents (Claude Code, Cursor, Codex, and others). Each skill is a set of markdown files that give AI tools deep knowledge of established design frameworks, heuristics, and methodologies. There is no build system, no tests, and no application code — this is a pure content repository.

The repo ships through two distribution channels at once, from one copy of the content:

- **`npx skills add cuellarfr/design-skills`** — the [Vercel skills CLI](https://github.com/vercel-labs/skills), which walks the repo for `SKILL.md` files. Works with Claude Code, Cursor, Codex, and 40+ other agents.
- **Claude Code plugin** — `/plugin marketplace add cuellarfr/design-skills`, then `/plugin install design-skills@design-skills`.

## Skill Architecture

Every skill lives under `skills/` and follows the same structure:

```
skills/skill-name/
├── SKILL.md              # Main file (200-350 lines), standalone
├── references/            # Deep reference material, loaded on demand
├── templates/             # Fillable deliverable templates
└── examples/              # End-to-end walkthroughs and scenarios
```

SKILL.md files use YAML frontmatter with `name` and `description` fields. The description is what agents use to decide when to load the skill.

**`name` must be kebab-case and match the directory name.** The skills CLI slugifies the frontmatter `name` to decide the installed directory, so a mismatch installs the skill under a different folder than the one it lives in here.

## Plugin Packaging

`.claude-plugin/` holds both manifests, and nothing else — per Claude Code's rules, `skills/` must stay at the repo root, never inside `.claude-plugin/`.

- `.claude-plugin/plugin.json` — plugin manifest. `name: design-skills` is the namespace, so skills resolve as `/design-skills:accessibility-audit`.
- `.claude-plugin/marketplace.json` — makes the repo its own single-plugin marketplace via `"source": "./"`, so users can install without waiting on the community catalog.

Bump `version` in **both** files together when publishing; Claude Code only offers users an update when it changes.

Validate packaging changes with `claude plugin validate . --strict`, and confirm the CLI path still resolves all ten skills with `npx skills add . --list`.

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
- `.claude-plugin/` — Plugin and marketplace manifests (see Plugin Packaging above)
- `LICENSE` — MIT
