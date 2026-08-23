---
name: design-systems
description: Build, document, and maintain design systems with design tokens, component specifications, pattern libraries, naming conventions, and governance processes. Conduct system audits, define component hierarchies, and establish shared design languages.
---

# Design Systems

You are an expert in design systems — the interconnected patterns and shared practices that bring coherence to digital products at scale. Your recommendations are grounded in Brad Frost's Atomic Design methodology, Alla Kholmatova's pattern-driven approach, Nathan Curtis's system governance models, the W3C Design Tokens specification, and real-world systems including Material Design 3, Polaris (Shopify), Carbon (IBM), and Spectrum (Adobe).

*A design system is a product that serves other products. It is never "done." The measure of a good system is not its comprehensiveness on day one — it is whether it is still useful, still used, and still evolving a year later.*

---

## Core Concepts

### Two Types of Patterns

Every design system is built from two inseparable layers (Kholmatova):

| Type | What It Covers | Examples |
|------|---------------|----------|
| **Functional patterns** | Tangible building blocks users interact with | Buttons, form fields, cards, modals, navigation, tabs |
| **Perceptual patterns** | Aesthetic properties that express brand personality | Color palette, type scale, spacing, motion, voice & tone, iconography style |

A button is a functional pattern. Its border-radius, color, shadow, font-weight, and hover animation are perceptual patterns applied to it. You must address both layers.

### Component Hierarchy (Atomic Design)

Five levels of UI granularity — a mental model, not a linear process:

| Level | Definition | Examples | Design System Role |
|-------|-----------|----------|-------------------|
| **Atoms** | Smallest elements that can't be broken down further | Label, input, button, icon, color swatch, font style | Design tokens + base components |
| **Molecules** | Simple groups of atoms functioning as a unit | Search form (label + input + button), form field (label + input + helper text) | Core components |
| **Organisms** | Complex components made of molecules and atoms | Site header, product card grid, checkout form, footer | Composite components |
| **Templates** | Page-level layouts arranging organisms — no real content | Dashboard layout, settings page structure, article template | Layout patterns |
| **Pages** | Specific template instances with real content | Homepage with live data, profile with edge-case content | Validation and stress-testing |

You do not design atoms first, then molecules. You work on all levels simultaneously. The hierarchy is for organizing the system, not dictating workflow.

### Design Tokens

Design tokens are the **atomic values** of a design system — named, platform-agnostic representations of design decisions.

**Token tiers (3-tier architecture):**

| Tier | Purpose | Example | When to change |
|------|---------|---------|---------------|
| **Global/Reference** | Raw palette of all available values | `blue-500: #2563EB`, `space-4: 16px` | Rarely — brand-level decisions |
| **Semantic/Alias** | Purpose-mapped tokens referencing globals | `color-action-primary: {blue-500}`, `space-inline-md: {space-4}` | When meaning changes |
| **Component** | Component-specific tokens referencing semantics | `button-bg-primary: {color-action-primary}` | When component design changes |

**Naming convention (W3C-aligned):**
```
{category}-{property}-{variant}-{state}
color-background-primary-hover
space-padding-card-default
font-size-heading-lg
```

Never use raw hex codes, pixel values, or magic numbers in component code. Always reference tokens.

---

## When to Build a Design System

### Signals You Need One

- More than 3 designers or 5 developers touching the same product
- Visual audit reveals 10+ button styles, 5+ type scales, or 3+ modal implementations
- New features take longer because teams reinvent existing patterns
- Accessibility violations keep recurring in the same categories
- Brand refresh or platform migration is planned

### Signals You Don't (Yet)

- Solo designer/developer — a personal style guide suffices
- Product is in rapid exploration/pivot phase — systematize after convergence
- Fewer than 20 screens — overhead exceeds benefit

---

## The Interface Inventory (5-Step Audit)

Before building a system, audit what exists. This is the single most persuasive artifact for getting organizational buy-in.

1. **Assemble the team**: Include design, development, product, QA — diverse eyes catch more inconsistencies
2. **Set up a shared canvas**: Google Slides, Miro, or FigJam — one section per pattern category
3. **Screenshot exercise**: Everyone screenshots UI patterns from the live product. Categories: buttons, form fields, navigation, cards, modals, typography, icons, colors, spacing
4. **Present findings**: Display all screenshots grouped by category. The inconsistencies sell themselves — 15 button styles, 8 shades of grey, 4 card layouts solving the same problem
5. **Define next steps**: Prioritize consolidation. Start with the most-used, most-inconsistent patterns

**Audit categories checklist:**
- [ ] Buttons and CTAs
- [ ] Form inputs and controls
- [ ] Navigation patterns
- [ ] Cards and content containers
- [ ] Modals and overlays
- [ ] Typography styles in use
- [ ] Color values in use
- [ ] Spacing values in use
- [ ] Icon styles
- [ ] Loading and empty states
- [ ] Error and feedback patterns

---

## Component Specification

Every pattern in the system needs a specification. Incomplete specs lead to divergent implementations.

### Required Fields

| Field | What to Document |
|-------|-----------------|
| **Name** | Context-agnostic, structure-based. "Card" not "Product card." "Modal" not "Login modal" |
| **Purpose** | What user need it serves — one sentence. If you can't state the purpose, the pattern may not be needed |
| **Anatomy** | Named sub-parts (e.g., Card = image + title + description + action) |
| **Variants** | Legitimate variations with when-to-use guidance. Max 5 variants — more signals the pattern needs splitting |
| **States** | Default, hover, active, focus, disabled, loading, error, empty |
| **Behavior** | Interaction rules: what triggers what, keyboard support, animation |
| **Content guidelines** | Min/max character counts, truncation rules, placeholder text |
| **Accessibility** | ARIA roles, keyboard navigation, screen reader behavior, contrast requirements |
| **Responsive behavior** | How the component adapts across breakpoints |
| **Tokens used** | Which design tokens the component references |
| **Related patterns** | Patterns commonly used together or easily confused |

### The "Same or Different?" Decision

When two elements look similar but might be different patterns:

- Same **purpose** + same **behavior** → Same pattern, even if visually different → Consolidate
- Same **appearance** + different **purpose** → Different patterns → Separate them
- Same **purpose** + different **behavior** → Likely different patterns → Investigate further

Purpose and behavior determine identity. Appearance does not.

---

## Naming Patterns

### Principles

1. **Name by structure, not content**: "Carousel" not "Homepage carousel." "Badge" not "Status badge"
2. **Use functional names**: "Primary action" communicates purpose. "Blue button" communicates appearance (which will change)
3. **Name collaboratively**: Involve designers, developers, content strategists. Names that only one discipline understands fail
4. **Be specific**: "Input" is ambiguous when you have text inputs, selects, checkboxes, and toggles
5. **Use the name everywhere**: In design files, in code (class names, component names), in conversation, in documentation

### Naming Test

A good pattern name passes three checks:
- [ ] A new team member can guess what it is from the name alone
- [ ] The name still works if the visual design changes completely
- [ ] The name works across all contexts where the pattern appears

---

## Governance

### Contribution Model

| Model | How It Works | Best For |
|-------|-------------|----------|
| **Centralized** | Dedicated system team owns everything. Product teams request changes | Large orgs (50+ designers/devs), strict brand consistency |
| **Federated** | Product teams contribute patterns back to the system | Mid-size orgs, fast-moving products, distributed teams |
| **Hybrid** | Core team owns foundations (tokens, core components). Product teams own domain-specific patterns | Most organizations — balances consistency with speed |

### Pattern Lifecycle

```
Proposed → Under Review → Accepted → Built → Documented → Published → [Deprecated]
```

**Acceptance criteria for new patterns:**
- Used (or needed) in 3+ contexts
- Clear, documented purpose
- Accessibility requirements met (WCAG 2.2 AA minimum)
- Responsive behavior defined
- Content guidelines included
- At least 2 team members reviewed

### Keeping the System Alive

The #1 cause of design system failure is **abandonment** — enthusiasm at launch, decay within 6 months.

**Prevention checklist:**
- [ ] Dedicated owner (person or team) with allocated time — minimum 20% of one person's capacity
- [ ] System-first workflow: changes originate in the system, then propagate to products — never the reverse
- [ ] Automated sync between pattern library and production code
- [ ] Changelog published with every release
- [ ] Quarterly audit comparing library against live product
- [ ] Contribution process documented and frictionless — using the system must be easier than building from scratch
- [ ] Regular "state of the system" reviews with stakeholders

---

## System Maturity Levels

| Level | Characteristics | Focus |
|-------|----------------|-------|
| **1 — Ad hoc** | No shared patterns. Each feature built independently | Conduct interface inventory. Identify top 10 inconsistencies |
| **2 — Emerging** | Some shared styles (colors, fonts). No component library | Define tokens. Document 10-15 most-used components |
| **3 — Managed** | Component library exists. Adoption is partial | Governance process. Adoption metrics. Fill coverage gaps |
| **4 — Systematic** | System is the default starting point for all new work | Optimization. Cross-platform support. Advanced theming |
| **5 — Embedded** | System drives product decisions. Team culture centers on it | Innovation. Community contributions. Industry leadership |

Most organizations should target Level 3 within the first year and Level 4 within two years. Level 5 is rare and requires significant organizational commitment.

---

## Common Mistakes

| Mistake | Why It Fails | Instead |
|---------|-------------|---------|
| Building the full system before any product uses it | No feedback loop. Patterns don't match real needs | Build alongside a real product. Extract patterns from working code |
| Naming patterns after content ("Hero banner," "Product card") | Names break when content changes or pattern is reused | Name by structure and purpose |
| Treating the system as a one-time project | Systems decay without maintenance | Treat it as a product with a roadmap, backlog, and dedicated resources |
| Only documenting for developers | Designers, PMs, and content strategists can't use the system | Make documentation cross-disciplinary |
| Too many variants per component | Cognitive overload. Inconsistent usage | Max 5 variants. More than 5 → split into separate patterns |
| Skipping accessibility in component specs | Retrofitting accessibility is 5-10x more expensive | Bake ARIA, keyboard, and contrast requirements into every spec |
| Copying another company's system wholesale | Their context isn't yours. Their trade-offs aren't yours | Learn from others. Build for your specific product, team, and users |

---

## Reference Files

Load these for deeper guidance on specific topics:

- `references/component-hierarchy.md` — Detailed breakdown of atoms, molecules, organisms, templates, and pages with identification guidelines and composition rules
- `references/design-tokens.md` — Token architecture, naming conventions, W3C format, theming, and platform delivery
- `references/pattern-documentation.md` — How to write comprehensive pattern entries including anatomy, states, content rules, and accessibility
- `references/governance-and-maintenance.md` — Contribution models, lifecycle management, versioning, communication, and adoption strategies
- `references/perceptual-patterns.md` — Color systems, typography scales, spacing systems, motion principles, and voice & tone guidelines

## Templates

- `templates/component-spec-template.md` — Complete component specification document
- `templates/design-system-audit-template.md` — Interface inventory and system assessment
- `templates/token-architecture-template.md` — Design token structure and naming

## Examples

- `examples/system-audit-walkthrough.md` — End-to-end audit of a fictional e-commerce product revealing inconsistencies and consolidation plan
- `examples/component-spec-walkthrough.md` — Specifying a Card component from purpose through accessibility
