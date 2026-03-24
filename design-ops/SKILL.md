---
name: design-ops
description: Run design sprints, manage handoff, establish team rituals, documentation standards, and design QA processes. Covers the operational side of design — how teams organize work, collaborate with engineering, and ship quality.
---

# Design Ops & Handoff

Operational processes that make design teams effective — sprints, handoff, rituals, documentation, and quality assurance.

---

## Design Sprints

A 5-day process for solving big problems and testing ideas before committing engineering resources. Based on Jake Knapp's Sprint methodology developed at Google Ventures.

### When to Sprint

| Signal | Sprint Is Right | Sprint Is Wrong |
|--------|----------------|-----------------|
| Problem clarity | Big problem, unclear solution | Solution already known — just build it |
| Stakes | High — wrong direction costs months | Low — easy to course-correct later |
| Team alignment | Disagreement on approach | Team already aligned |
| Time pressure | Need answers this week | Can run a longer discovery process |
| Complexity | Cross-functional problem | Single-discipline task |

### The 5-Day Structure

| Day | Focus | Key Activity | Output |
|-----|-------|-------------|--------|
| **Monday** | Map | Define the challenge, set a 2-year goal, map the problem space, pick a target | Sprint questions, problem map, target area |
| **Tuesday** | Sketch | Review existing solutions, each person sketches solutions individually | Solution sketches (one per person) |
| **Wednesday** | Decide | Present sketches, vote (dot voting + decider picks), create storyboard | Storyboard for prototype |
| **Thursday** | Prototype | Build a realistic facade — just enough to test | Testable prototype |
| **Friday** | Test | 5 user interviews, observe together, identify patterns | Go/no-go decision with evidence |

### Sprint Team

| Role | Count | Responsibility |
|------|-------|---------------|
| **Decider** | 1 | Has authority to make final calls. Usually PM or founder |
| **Facilitator** | 1 | Runs the process, keeps time, manages energy |
| **Designer** | 1-2 | Leads sketching, builds prototype |
| **Engineer** | 1-2 | Feasibility gut-checks, helps prototype |
| **Domain expert** | 1-2 | Customer support, sales, marketing — whoever knows the user |
| **Total** | 5-7 | More than 7 is counterproductive |

### Sprint Rules

1. **No devices** during working sessions — full attention
2. **Work alone together** — individual sketching, not group brainstorming
3. **The Decider decides** — democracy is slow; one person breaks ties
4. **Prototype, don't build** — facade quality, not production quality
5. **5 users is enough** — you'll see 85% of usability issues with 5 participants

---

## Design-to-Development Handoff

Handoff is the #1 source of quality loss in product teams. The goal: engineers should never have to guess.

### Handoff Maturity Levels

| Level | Description | Symptom |
|-------|------------|---------|
| **1. Screenshot** | Designer sends a static image | Engineers guess spacing, states, behavior |
| **2. Annotated mockup** | Redlines, spacing callouts | Better, but still missing states and edge cases |
| **3. Interactive spec** | Figma/design tool with inspect mode, component links | Engineers can extract values, but behavior is undocumented |
| **4. Full spec** | All states, transitions, error handling, responsive behavior, tokens | Engineers build exactly what was designed |
| **5. Integrated** | Design and code share a component system; handoff is a conversation, not a document | Minimal spec needed — shared language does the work |

**Target: Level 4 minimum. Level 5 for mature teams.**

### What a Complete Handoff Includes

Every screen or component handoff must cover:

| Category | Required Items |
|----------|---------------|
| **Layout** | Spacing (in tokens, not pixels), alignment, responsive breakpoints, container behavior |
| **Content** | Final copy (not lorem ipsum), character limits, truncation rules, localization notes |
| **States** | Default, hover, focus, active, disabled, loading, empty, error, success — for every interactive element |
| **Behavior** | What happens on click/tap, keyboard interaction, drag, swipe. Transition details |
| **Responsive** | How the layout adapts at each breakpoint. What reflows, stacks, hides, or changes |
| **Tokens** | Color tokens, typography tokens, spacing tokens — never raw hex/px values |
| **Accessibility** | Focus order, ARIA roles, screen reader announcements, touch targets, color contrast |
| **Edge cases** | Long strings, empty data, error recovery, offline behavior, permissions |
| **Assets** | Icons (SVG), images (with alt text), animations (specs or files) |

### Handoff Anti-Patterns

| Anti-Pattern | Problem | Fix |
|-------------|---------|-----|
| "It's in Figma" | No context, engineer must reverse-engineer intent | Write behavior notes on every frame |
| Happy path only | Only the ideal flow is designed | Design all states before handoff |
| Pixel specs | "24px left margin" | Use tokens: `spacing-md` |
| Verbal handoff | "I'll explain it in standup" | If it's not written down, it doesn't exist |
| Big-bang handoff | Entire feature dropped on engineering at once | Hand off in slices that match sprint stories |
| No error states | "We'll figure out errors later" | Error states are designed first, not last |

---

## Team Rituals and Cadences

### Core Design Rituals

| Ritual | Frequency | Duration | Purpose | Who Attends |
|--------|-----------|----------|---------|-------------|
| **Design critique** | Weekly | 45-60 min | Improve work-in-progress through structured feedback | All designers |
| **Design-eng sync** | Weekly | 30 min | Align on upcoming work, resolve handoff questions | Design lead + eng lead |
| **Design review** | Per milestone | 30-60 min | Stakeholder sign-off on direction | PM, design, eng leads, stakeholders |
| **Handoff session** | Per story/feature | 30-45 min | Walk engineering through specs, answer questions | Designer + implementing engineers |
| **Design QA** | Per release | 60-90 min | Verify implementation matches spec | Designer + engineer |
| **Retro** | Bi-weekly or per sprint | 45 min | Improve the process | Whole product team |
| **Design sprint** | As needed | 5 days | Solve big problems, validate risky ideas | Cross-functional team (5-7) |

### Running Effective Design Critiques

**Format:** Presenter shares context (2 min) → Group reviews silently (3 min) → Structured feedback (15-20 min per piece) → Next steps (2 min)

**Critique rules:**
1. Presenter states what feedback they want — "I need help with the empty state" not "What do you think?"
2. Feedback references principles, not preferences — "This violates Fitts's Law" not "I don't like the button placement"
3. Describe problems, don't prescribe solutions — "Users might miss this action" not "Make the button bigger"
4. No defending — presenter listens, asks clarifying questions only
5. Written notes — someone captures all feedback items with action owners

### Handoff Session Structure

1. **Context** (5 min) — What problem does this solve? What user story?
2. **Walkthrough** (10-15 min) — Designer walks through the flow, screen by screen
3. **States and edge cases** (10 min) — Hover, error, empty, loading, responsive
4. **Tokens and components** (5 min) — Which design system components to use, which tokens
5. **Questions** (10 min) — Engineers ask anything unclear
6. **Action items** — What needs clarification before build starts

---

## Documentation Standards

### File Organization

```
project-name/
├── exploration/          # Early concepts, discarded directions
│   └── v1-concepts/
├── current/              # Active, approved designs
│   ├── flows/            # User flows and journey maps
│   ├── screens/          # Screen-level designs
│   └── components/       # Component-level specs
├── assets/               # Production-ready exports
│   ├── icons/
│   └── images/
├── handoff/              # Handoff documentation
│   └── [feature-name]/
└── archive/              # Past versions (never delete, move here)
```

### Naming Conventions

| Element | Convention | Example |
|---------|-----------|---------|
| Files | `[project]-[feature]-[variant]` | `taskpilot-onboarding-v2` |
| Pages/frames | `[flow]-[step]-[state]` | `checkout-payment-error` |
| Components | Match code component names exactly | `ButtonPrimary`, not `Main CTA` |
| Versions | Semantic: `v1.0`, `v1.1`, `v2.0` | Major = new direction, minor = iteration |
| Layers | Descriptive, no "Group 1" or "Frame 47" | `header/nav/menu-trigger` |

### Version Control Rules

1. **Never overwrite** — create a new version, archive the old one
2. **Name the change** — "v2.1 — added error states" not just "v2.1"
3. **Link to decisions** — every major version links to the decision that drove it (Slack thread, meeting note, sprint review)
4. **Single source of truth** — one canonical file per feature. No "copy of" files
5. **Archive, don't delete** — move outdated designs to archive with a date stamp

---

## Design QA

Design QA is the process of verifying that what was built matches what was designed. Do it before every release.

### Design QA Checklist

| Category | Check | Tool |
|----------|-------|------|
| **Visual accuracy** | Colors match tokens. Spacing matches spec. Typography is correct | Side-by-side comparison, browser dev tools |
| **States** | All states render correctly: default, hover, focus, active, disabled, error, loading, empty | Manual testing, Storybook |
| **Responsive** | Layout works at all breakpoints. Nothing overflows, truncates wrong, or disappears | Resize browser, test on real devices |
| **Content** | Real content fits. Long strings handled. Empty states designed. Truncation works | Test with edge-case content |
| **Interaction** | Animations match spec. Transitions are smooth. Timing feels right | Manual testing, slow-motion recording |
| **Accessibility** | Focus order correct. Screen reader announces correctly. Contrast passes. Touch targets 44px+ | axe, keyboard testing, VoiceOver/NVDA |
| **Cross-browser** | Renders correctly in Chrome, Firefox, Safari, Edge | BrowserStack or manual |
| **Performance** | Images optimized. No layout shift. Animations don't drop frames | Lighthouse, Core Web Vitals |

### Filing Design QA Issues

Every issue needs:

```
**What:** [Element name] on [screen/page]
**Expected:** [What the design spec shows — link to frame]
**Actual:** [What the build shows — screenshot]
**Severity:** [Critical / Major / Minor / Cosmetic]
**Environment:** [Browser, viewport, OS]
```

**Severity scale:**
- **Critical** — Functionality broken. User can't complete the task
- **Major** — Wrong behavior. User can complete the task but with confusion or errors
- **Minor** — Visual discrepancy. User isn't affected functionally but quality feels off
- **Cosmetic** — Nitpick. Pixel-level differences that only designers notice

### Acceptance Criteria for Design

Add these to every user story:

```
Design acceptance criteria:
- [ ] All states match design spec (link to Figma frame)
- [ ] Responsive behavior verified at 320px, 768px, 1024px, 1440px
- [ ] Keyboard navigation works (Tab, Enter, Escape, Arrow keys)
- [ ] Screen reader announces all interactive elements correctly
- [ ] Design tokens used (no hardcoded colors, spacing, or typography)
- [ ] Loading and error states implemented
- [ ] Edge-case content tested (empty, long strings, special characters)
```

---

## Process Metrics

Track these to measure design ops health:

| Metric | What It Measures | Target | How to Measure |
|--------|-----------------|--------|----------------|
| **Handoff completeness** | % of handoffs with all states, tokens, responsive specs | >90% | Audit handoff docs quarterly |
| **Design QA pass rate** | % of stories passing design QA on first review | >80% | Track QA issues per story |
| **Rework rate** | % of design work that gets redone after handoff | <15% | Count post-handoff design changes |
| **Sprint velocity impact** | How often missing specs block engineering | 0 blocks/sprint | Track blocker tags in standup |
| **Design debt** | Known visual/interaction inconsistencies in production | Decreasing trend | Maintain a design debt backlog |
| **Critique participation** | Designers bringing work to critique regularly | 100% monthly | Track critique presenters |

---

## Common Mistakes

| Mistake | Why It Fails | Better Approach |
|---------|-------------|----------------|
| Skipping the sprint map day | Team builds solutions to the wrong problem | Monday's map and target selection is the most valuable day |
| Designing in isolation | Work handed off doesn't match engineering reality | Daily or weekly design-eng syncs |
| No design QA process | Visual quality degrades over time | QA every story, not just every release |
| Over-documenting | 30-page spec nobody reads | Spec what's ambiguous. Shared component system handles the rest |
| Under-documenting | "You can see it in Figma" | If an engineer has to ask, the spec was incomplete |
| Treating handoff as a one-time event | Throws work over the wall | Handoff is a conversation that continues through implementation |
| No retros | Same mistakes repeat | Bi-weekly retros with specific action items and owners |
| Design critique as approval gate | Critique becomes political | Critique is for improving work, not for approving it |
