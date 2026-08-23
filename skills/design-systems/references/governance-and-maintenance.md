# Governance and Maintenance

A design system without governance decays within 6 months. This reference covers contribution models, lifecycle management, versioning, communication, and adoption strategies.

---

## Contribution Models

### Centralized

A dedicated design system team owns everything. Product teams consume the system and request changes through a formal process.

**Structure:**
- 3-8 person core team (designers + developers + documentation lead)
- Product teams submit requests via issue tracker
- Core team prioritizes, builds, and publishes

**Strengths:**
- Maximum consistency
- Deep expertise in system architecture
- Clear accountability

**Weaknesses:**
- Bottleneck: core team becomes a blocker when demand exceeds capacity
- Disconnected from product reality if team doesn't rotate in product work
- Slow to address product-specific needs

**Best for:** Large organizations (50+ designers/developers), strict brand requirements, regulated industries

### Federated (Distributed)

Product teams contribute patterns back to the system. Ownership is shared.

**Structure:**
- Small core team (1-3 people) sets standards and reviews contributions
- Product teams build patterns and submit them for inclusion
- "Design system guild" or working group meets regularly

**Strengths:**
- Faster innovation — patterns come from real product needs
- Broader ownership and buy-in
- Scales with the organization

**Weaknesses:**
- Consistency requires active review and enforcement
- Contribution quality varies — need clear standards
- Coordination overhead increases with team count

**Best for:** Mid-size organizations, fast-moving products, distributed teams

### Hybrid (Recommended Default)

Core team owns foundations (tokens, core components, documentation standards). Product teams own domain-specific patterns and contribute candidates back.

**Structure:**
- Core team: 2-5 people maintaining tokens, core components, tooling, documentation
- Product teams: build on foundations, propose new patterns when used in 3+ contexts
- Contribution guidelines define the handoff process

**Strengths:**
- Balances consistency with speed
- Core team isn't a bottleneck for product-specific patterns
- Natural path for patterns to graduate from product-level to system-level

**Best for:** Most organizations

---

## Pattern Lifecycle

### Stages

```
1. PROPOSED    → Someone identifies a need for a new pattern
2. UNDER REVIEW → Core team evaluates against acceptance criteria
3. ACCEPTED    → Pattern approved for building
4. BUILT       → Implementation complete in code and design tools
5. DOCUMENTED  → Full documentation published in pattern library
6. PUBLISHED   → Available for general use (Stable)
7. DEPRECATED  → Marked for removal with migration path
8. REMOVED     → Deleted from the system after deprecation period
```

### Acceptance Criteria for New Patterns

A proposed pattern should meet **all** of these before being accepted:

- [ ] Used (or needed) in **3+ distinct contexts** — if it's used in only one place, it's a product component, not a system pattern
- [ ] **Purpose** is clearly stated in one sentence
- [ ] Does not duplicate an existing pattern — explain why existing patterns don't work
- [ ] **Accessibility** requirements meet WCAG 2.2 AA minimum
- [ ] **Responsive** behavior defined for all breakpoints
- [ ] **Content guidelines** included
- [ ] Reviewed by at least **2 team members** from different disciplines

### Deprecation Process

Deprecation must be gradual and communicated. Never remove a pattern without warning.

**Timeline:**
1. **Announce deprecation** — Add "Deprecated" badge to pattern library entry. State the replacement pattern and migration path
2. **Migration period** — Minimum 2 sprints (for small systems) or 1 quarter (for large systems). Add console warnings or linter rules flagging usage
3. **Usage audit** — Before removal, verify zero active usage. If usage remains, extend the period or provide migration support
4. **Remove** — Delete pattern from library and codebase. Update changelog

**Deprecation notice template:**
```
⚠️ DEPRECATED as of [version]
Replacement: [New Pattern Name]
Migration guide: [link]
Removal planned: [date or version]
Reason: [brief explanation]
```

---

## Versioning

### Semantic Versioning for Design Systems

Apply semver to the design system as a product:

| Change Type | Version Bump | Examples |
|-------------|-------------|----------|
| **Patch** (x.x.X) | Bug fixes, documentation updates, minor visual tweaks that don't change API | Fix button focus ring visibility, update spacing in tooltip |
| **Minor** (x.X.0) | New patterns, new variants, new tokens — backwards compatible | Add "compact" card variant, new semantic color token |
| **Major** (X.0.0) | Breaking changes — pattern removal, renamed tokens, restructured API | Remove deprecated `Banner` pattern, rename `color-primary` to `color-action-primary` |

### Versioning Rules

1. **Never introduce breaking changes in a minor release**
2. **Group breaking changes into major releases** — one painful migration is better than five small ones
3. **Provide migration guides** for every major release
4. **Maintain the previous major version** for at least one quarter after a new major release
5. **Communicate breaking changes at least 2 sprints before the release**

---

## Communication

### Channels

| Audience | Channel | Frequency |
|----------|---------|-----------|
| **All consumers** | Changelog / release notes | Every release |
| **Active contributors** | Slack/Teams channel + weekly sync | Weekly |
| **Stakeholders** | State of the system report | Quarterly |
| **New team members** | Onboarding guide + pairing session | On hire |
| **Entire organization** | Design system newsletter or demo | Monthly or quarterly |

### Changelog Format

```markdown
## [2.3.0] - 2026-03-15

### Added
- Compact variant for Card component
- `color-feedback-info` semantic token
- Date Picker pattern (Beta)

### Changed
- Button focus ring increased from 1px to 2px for accessibility
- Modal backdrop opacity reduced from 60% to 50%

### Deprecated
- `Banner` pattern — use `Alert` instead. Removal in v3.0.0.

### Fixed
- Tooltip positioning overflow on small viewports
- Select dropdown z-index conflict with Modal
```

### What to Communicate

- **New patterns**: What, why, when to use, link to docs
- **Changes to existing patterns**: What changed, why, impact on consumers
- **Deprecations**: What's deprecated, replacement, migration timeline
- **Roadmap updates**: What's coming, what's been reprioritized, why
- **Adoption wins**: "Team X reduced their build time by 30% using the new Form components"

---

## Adoption Strategy

### Measuring Adoption

| Metric | How to Measure | Target |
|--------|---------------|--------|
| **Component coverage** | % of UI built with system components vs. custom | >80% for mature products |
| **Token coverage** | % of design values referencing tokens vs. hardcoded | >95% |
| **Pattern library usage** | Page views, search queries, unique visitors per week | Trending upward |
| **Contribution rate** | PRs / issues submitted by product teams per quarter | At least 1 per team per quarter |
| **Time to first component** | How long it takes a new developer to ship using the system | Under 1 day |
| **Consistency score** | Visual audit of live product vs. system spec | Quarterly improvement |

### Driving Adoption

**Make it the path of least resistance:**
- Using the system should be faster than building from scratch
- Provide starter templates, code generators, and Figma libraries
- Integrate with the team's existing toolchain (npm package, Figma plugin, IDE snippets)

**Remove friction:**
- Zero-config setup: `npm install @company/design-system` and go
- Comprehensive documentation with copy-paste code examples
- Responsive, accessible defaults — consumers shouldn't have to add accessibility themselves

**Create advocates:**
- Identify power users on product teams and empower them as "system champions"
- Run office hours where anyone can get help
- Pair with product teams during their sprints to show how the system accelerates work

**Show value:**
- Track and publish time savings: "Average feature delivery is 2 days faster using system components"
- Celebrate contributions publicly
- Report accessibility improvements: "WCAG violations down 60% since system adoption"

### Anti-patterns in Adoption

| Anti-pattern | Problem | Instead |
|-------------|---------|---------|
| Mandating adoption without support | Teams feel imposed upon, find workarounds | Provide training, pairing, and migration support |
| Building in isolation for 6 months then "launching" | System doesn't match real product needs | Build alongside a real product. Ship incrementally |
| Measuring only component count | 200 components with 5% adoption is worse than 30 with 80% | Measure adoption rate and consumer satisfaction |
| Ignoring feedback from product teams | Consumers feel unheard, build their own components | Structured feedback loops — surveys, retros, issue tracker |

---

## Team Health Checks

Run these quarterly with the core team and key consumers:

### For the core team
- [ ] Is the backlog manageable? (Under 30 open issues)
- [ ] Are we shipping on a regular cadence? (At least 1 release per month)
- [ ] Is documentation keeping up with implementation?
- [ ] Are deprecated patterns being migrated on schedule?
- [ ] Do we have visibility into how the system is being used?

### For consumers
- [ ] Can you find what you need in the pattern library within 2 minutes?
- [ ] Does the system cover 80%+ of your UI needs?
- [ ] Do you know how to propose a new pattern?
- [ ] Do you receive timely updates about changes?
- [ ] Is the system making your work faster?

A "no" on any item is a priority item for the next quarter's roadmap.
