# Design Skills for Claude Code

A collection of UX and design skills for [Claude Code](https://docs.anthropic.com/en/docs/claude-code). These skills give Claude deep knowledge of established design frameworks, heuristics, and methodologies — turning it into an informed design partner rather than a generic assistant.

Each skill follows the same architecture: a main `SKILL.md` file that works standalone, plus `references/`, `templates/`, and `examples/` directories that provide depth on demand.

## Skills

### UX Research
Plan, conduct, and analyze user research using proven methodologies.

Covers generative, evaluative, and continuous discovery research. Includes interview scripting, usability test planning, participant recruiting, qualitative analysis (affinity diagrams, thematic analysis), and synthesis into personas, journey maps, and opportunity maps.

**Key references:** 20+ research methods catalog, interviewing techniques, usability testing with SUS scoring (full 10-question scale, scoring formula, grade interpretation), workshop facilitation methods (HMW, Creative Matrix, Dot Voting, and 12 more), continuous discovery (Opportunity Solution Trees, assumption testing).

`14 files` · `3,270 lines`

### Design Critique & Evaluation
Evaluate UI designs against usability heuristics, UX laws, interaction patterns, and interaction design principles.

Provides a structured 7-step critique framework grounded in Nielsen's 10 heuristics, 27 UX laws organized by design domain, established usability checks, and interaction design principles (product posture, perpetual intermediates, excise audits, orchestration).

**Key references:** 50+ interaction patterns catalog with use/don't-use guidance, heuristics and laws deep reference, visual design principles (hierarchy, typography, color, spacing), interaction design principles.

`10 files` · `2,384 lines`

### Accessibility Audit
Conduct accessibility audits against WCAG 2.2 guidelines.

A 5-layer audit process (automated, keyboard, screen reader, visual, flow) covering conformance at A, AA, and AAA levels. Identifies issues, assesses severity, provides code fixes, and generates audit reports.

**Key references:** Complete WCAG 2.2 checklist reorganized into 11 audit task groups, 15 common issues with before/after code examples, testing tools comparison (axe, WAVE, Lighthouse, Pa11y), CI/CD integration code, keyboard and screen reader test scripts.

`8 files` · `2,175 lines`

### Journey Mapping
Create customer journey maps, service blueprints, experience maps, empathy maps, and other alignment diagrams.

Guides diagram type selection across 7 diagram types, content structure, illustration syntax, and alignment workshops. Based on established alignment diagram methodology and service design practice.

**Key references:** Customer journey maps (8 required + 7 optional elements), service blueprints (5 swimlanes, 3 lines), experience maps and mental models, alignment workshop facilitation (half-day and full-day formats).

`10 files` · `2,297 lines`

### Design Elevation
Transform functional visual outputs into polished, professional designs.

Applies systematic design thinking to any visual output — presentations, spreadsheets, dashboards, reports, HTML, PDFs, web pages, and data visualizations. References best practices from Stripe, Linear, Apple, Bauhaus, and Swiss design.

**Key references:** Typography scales, color systems, spacing systems, grid systems, design interrogation protocol, technique catalog, design exemplars.

`9 files` · `3,208 lines`

## Installation

### Install all skills

```bash
# Clone the repo
git clone https://github.com/cuellarfr/design-skills.git

# Copy all skills to your Claude Code skills directory
cp -r design-skills/*/ ~/.claude/skills/
```

### Install a single skill

```bash
# Example: install only the design critique skill
cp -r design-skills/design-critique ~/.claude/skills/
```

### Verify installation

Skills are automatically detected by Claude Code. After copying, start a new conversation and the skills will appear in the available skills list. You can verify by asking Claude:

```
What design skills do you have available?
```

## Skill Architecture

Each skill follows a consistent structure:

```
skill-name/
├── SKILL.md              # Main skill file (200-350 lines)
│                          # Standalone — works without reference files
│                          # Contains frameworks, tables, checklists, quick references
│
├── references/            # Deep reference material (loaded on demand)
│   ├── topic-a.md         # Detailed coverage of a specific area
│   └── topic-b.md         # Each file is self-contained
│
├── templates/             # Fillable templates for deliverables
│   ├── report-template.md
│   └── checklist-template.md
│
└── examples/              # End-to-end walkthroughs
    ├── walkthrough.md      # Full worked example with fictional product
    └── scenarios.md        # Decision scenarios with rationale
```

**Design principles for these skills:**
- **Opinionated defaults** — Specific numbers, benchmarks, and rubrics rather than "consider..." language
- **Actionable over theoretical** — Every principle includes a concrete recommendation
- **Before/after examples** — Show what bad and good look like, with scoring
- **Progressive depth** — Main file is comprehensive standalone; reference files go deeper
- **Grounded in sources** — Built from established books and frameworks, not invented heuristics

## Sources

These skills synthesize material from established frameworks and standards:

- **Nielsen's 10 Usability Heuristics** — Heuristic evaluation framework and severity scales
- **Laws of UX** (lawsofux.com) — 27 UX laws organized by design domain
- **System Usability Scale (SUS)** — Standardized usability questionnaire and scoring methodology
- **Interaction design principles** — Product posture, perpetual intermediates, excise, orchestration, affordances
- **Alignment diagram methodology** — Journey maps, service blueprints, experience maps, ecosystem models
- **Service design principles** — Touchpoints, co-production, service ecology
- **Continuous discovery** — Opportunity Solution Trees, assumption testing, story-based interviewing
- **WCAG 2.2** — Web Content Accessibility Guidelines
- **WebAIM** — Million report data, contrast requirements, testing tools
- **LUMA Institute methods** — Workshop facilitation techniques

## License

MIT
