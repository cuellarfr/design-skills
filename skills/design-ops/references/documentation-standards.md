# Documentation Standards

Deep reference for organizing, naming, versioning, and maintaining design files and documentation.

---

## File Organization

### Project File Structure

Every project should follow a consistent structure regardless of tool:

```
[Project Name]/
├── 📁 Discovery
│   ├── Research findings
│   ├── Competitive analysis
│   ├── User flows (current state)
│   └── Problem framing artifacts
│
├── 📁 Exploration
│   ├── v1 concepts (discarded)
│   ├── v2 concepts (discarded)
│   └── Sketches and wireframes
│
├── 📁 Design (current, approved)
│   ├── User flows
│   ├── Screens (organized by flow or feature)
│   ├── Component specs (for new components)
│   └── Responsive variants
│
├── 📁 Handoff
│   ├── Sprint [N] handoff
│   ├── Sprint [N+1] handoff
│   └── Change requests
│
├── 📁 Assets
│   ├── Icons (SVG)
│   ├── Images (with alt text notes)
│   └── Animations (Lottie, GIF, or specs)
│
└── 📁 Archive
    ├── v1 (date, reason archived)
    └── v2 (date, reason archived)
```

### Figma File Structure

```
Figma File: [Project Name]
├── 📄 Cover Page (project name, status, owner, last updated, links)
├── 📄 Flows (user flow diagrams)
├── 📄 [Feature A] — Screens
│   ├── Section: Happy Path
│   ├── Section: Error States
│   ├── Section: Empty States
│   ├── Section: Loading States
│   └── Section: Responsive (Mobile / Tablet)
├── 📄 [Feature B] — Screens
│   └── (same section structure)
├── 📄 Components (feature-specific, not in the design system)
├── 📄 Exploration (discarded concepts — kept for reference)
└── 📄 Archive (previous versions)
```

### Cover Page Standard

Every Figma file should have a cover page with:

| Field | Example |
|-------|---------|
| **Project name** | TaskPilot — Onboarding Redesign |
| **Status** | 🟢 Active / 🟡 In Review / 🔴 On Hold / ⚪ Archived |
| **Owner** | Sarah Chen (designer) |
| **Last updated** | 2026-03-15 |
| **PM** | Alex Rivera |
| **Eng lead** | Jordan Kim |
| **Design system** | TaskPilot DS v2.3 |
| **Links** | PRD, Sprint board, Research findings, Prototype |
| **Changelog** | v2.1 — Added error states for payment flow (2026-03-15) |

---

## Naming Conventions

### File Naming

| Element | Pattern | Example |
|---------|---------|---------|
| **Figma files** | `[Product] — [Feature] [Version]` | `TaskPilot — Onboarding v2` |
| **Pages in Figma** | `[Feature or Section]` | `Checkout Flow`, `Components`, `Archive` |
| **Sections** | `[Category]` | `Happy Path`, `Error States`, `Mobile` |

### Frame Naming

Frames are the most important naming level — they appear in links, handoff tools, and search.

| Pattern | Example |
|---------|---------|
| `[Flow] / [Step] / [State]` | `Checkout / Payment / Default` |
| `[Flow] / [Step] / [State] / [Breakpoint]` | `Checkout / Payment / Error / Mobile` |
| `[Component] / [Variant] / [State]` | `Button / Primary / Hover` |

**Rules:**
- Use `/` as a separator (Figma auto-nests in the layers panel)
- Use title case: `Payment Method` not `payment method` or `PAYMENT METHOD`
- Use real names: `Checkout / Cart Summary` not `Frame 47` or `Screen 3`
- Include the state: `/ Default`, `/ Hover`, `/ Error`, `/ Loading`, `/ Empty`
- Include the breakpoint for responsive variants: `/ Desktop`, `/ Tablet`, `/ Mobile`

### Layer Naming

Layers inside frames should be descriptive:

| Bad | Good |
|-----|------|
| Group 1 | header |
| Frame 47 | card/product-info |
| Rectangle 3 | avatar-background |
| Vector 12 | icon/chevron-right |
| Text | price/total |

**Auto-layout frames** should be named by their content role, not their layout behavior: `navigation` not `horizontal-frame-1`.

### Component Naming

Components should match the code component names exactly:

| Design Name | Code Name | Match? |
|------------|-----------|--------|
| Button / Primary | ButtonPrimary | Yes |
| Main CTA | ButtonPrimary | No — rename in design |
| Card | ProductCard | No — be specific |
| Input | TextInput | No — match the code name |

**Variant naming** uses `property=value` pairs:
```
Button
  size=small, variant=primary, state=default
  size=small, variant=primary, state=hover
  size=small, variant=secondary, state=default
  ...
```

---

## Version Control

### Versioning Strategy

Use semantic versioning adapted for design:

| Version Type | When | Example |
|-------------|------|---------|
| **Major (v1 → v2)** | New direction. Significant redesign. Breaking change to the flow | v1.0 → v2.0: Complete checkout redesign |
| **Minor (v2.0 → v2.1)** | New feature added, new state designed, scope expansion | v2.0 → v2.1: Added gift card payment method |
| **Patch (v2.1 → v2.1.1)** | Bug fix, copy correction, visual polish, alignment fix | v2.1 → v2.1.1: Fixed truncation on long product names |

### Version Documentation

Every version milestone should include a changelog entry:

```
## v2.1 — Added error states for payment flow (2026-03-15)

Changes:
- Added declined card error state with retry flow
- Added network error state with offline fallback
- Updated copy on payment confirmation screen

Reason: User testing revealed confusion when payment failed silently

Approved by: Alex Rivera (PM) in sprint review 2026-03-12
Link: [Sprint review notes]
```

### Figma-Specific Version Control

| Action | How |
|--------|-----|
| **Save a named version** | File → Save to Version History → name it with the version number and a description |
| **Branch for exploration** | Use Figma branching for experimental work. Merge or discard. Don't pollute the main file |
| **Archive old work** | Move to the Archive page in the same file (keeps context) or to a separate archive file (reduces file size) |
| **Track changes** | Use the changelog on the cover page for human-readable history. Figma version history for granular changes |
| **Resolve conflicts** | When two designers edit the same file, review changes together before continuing. Figma's multiplayer handles most cases, but conflicting design decisions need human resolution |

---

## Documentation Types

### Design Decision Records

For significant design decisions, capture the reasoning:

```
## Decision: [Short title]

**Date:** [Date]
**Decider:** [Name]
**Status:** [Proposed / Accepted / Superseded by [link]]

### Context
[What situation prompted this decision?]

### Options Considered
1. [Option A] — [Pros / Cons]
2. [Option B] — [Pros / Cons]
3. [Option C] — [Pros / Cons]

### Decision
[What was decided and why]

### Consequences
[What this decision means for the product, the team, the design system]
```

### Pattern Usage Guidelines

When a new UI pattern is introduced, document how to use it:

```
## Pattern: [Name]

**When to use:** [Specific scenarios where this pattern applies]
**When NOT to use:** [Scenarios where a different pattern is better]
**Related patterns:** [Patterns that are similar or often confused]

### Example
[Screenshot or Figma link showing correct usage]

### Anti-example
[Screenshot or Figma link showing incorrect usage]
```

### Research Handoff

When research findings inform design work, document the connection:

```
## Research: [Study name]
**Date:** [Date]
**Method:** [Usability test / Interview / Survey / Analytics]
**Key findings:**
1. [Finding with supporting data]
2. [Finding with supporting data]

**Design implications:**
- [Finding 1] → [Specific design change]
- [Finding 2] → [Specific design change]

**Open questions:**
- [Question that needs further research]
```

---

## Documentation Maintenance

### Quarterly Audit

Every quarter, audit design documentation:

| Check | Action |
|-------|--------|
| **Orphaned files** | Files not linked to any active project → Archive or delete |
| **Outdated specs** | Designs that don't match production → Update or mark as historical |
| **Missing documentation** | Features in production with no design source → Create retrospective docs |
| **Naming violations** | Files or frames not following conventions → Rename |
| **Dead links** | Links to moved or deleted files → Fix or remove |
| **Stale cover pages** | Project status or owner out of date → Update |

### Documentation Ownership

| Document Type | Owner | Review Cadence |
|-------------|-------|---------------|
| **Project files** | Assigned designer | Per sprint |
| **Design system** | System owner/team | Weekly |
| **Decision records** | PM or design lead | Per decision |
| **Research docs** | Researcher | Per study |
| **Handoff specs** | Assigned designer | Per handoff |
| **Process docs** | Design ops / design lead | Quarterly |

### When to Delete vs. Archive

| Action | When |
|--------|------|
| **Archive** | Work was approved at some point. May need to reference it. Move to Archive page/folder |
| **Delete** | Scratch work, exploration that led nowhere, duplicate files, test files. Never shipped, never approved |
| **Keep active** | Currently in production or actively being developed |
