# Design System Audit: [Product Name]

**Date:** [Date]
**Auditor(s):** [Names and roles]
**Scope:** [Which product/pages/screens are included]

---

## 1. Current State Assessment

### System Maturity Level

| Level | Description | Current? |
|-------|------------|----------|
| 1 — Ad hoc | No shared patterns. Each feature built independently | [ ] |
| 2 — Emerging | Some shared styles (colors, fonts). No component library | [ ] |
| 3 — Managed | Component library exists. Adoption is partial | [ ] |
| 4 — Systematic | System is the default starting point for all new work | [ ] |
| 5 — Embedded | System drives product decisions. Team culture centers on it | [ ] |

### Team Context

| Factor | Answer |
|--------|--------|
| Number of designers | [#] |
| Number of front-end developers | [#] |
| Number of products/platforms | [#] |
| Dedicated design system team? | [Yes/No — size if yes] |
| Current tools | [Figma/Storybook/etc.] |

---

## 2. Interface Inventory

### Color Audit

| Context | Unique Values Found | Examples | Notes |
|---------|-------------------|----------|-------|
| Primary/brand | [#] | [Hex values] | |
| Text colors | [#] | [Hex values] | |
| Background colors | [#] | [Hex values] | |
| Border colors | [#] | [Hex values] | |
| Error/success/warning | [#] | [Hex values] | |

**Contrast violations found:** [Count and details]

### Typography Audit

| Context | Unique Values Found | Examples | Notes |
|---------|-------------------|----------|-------|
| Font families | [#] | [Names] | |
| Font sizes | [#] | [Values] | |
| Font weights | [#] | [Values] | |
| Line heights | [#] | [Values] | |

**Does a mathematical scale exist?** [Yes/No — ratio if yes]

### Spacing Audit

| Context | Unique Values Found | Follows a Scale? | Notes |
|---------|-------------------|-------------------|-------|
| Padding values | [#] | [Yes/No] | |
| Margin values | [#] | [Yes/No] | |
| Gap values | [#] | [Yes/No] | |

**Base unit identified?** [Yes/No — value if yes]

### Component Inventory

For each component category, count unique implementations:

| Category | Unique Variants Found | Should Be | Gap |
|----------|---------------------|-----------|-----|
| Buttons | [#] | [Target #] | [Consolidate/Split/OK] |
| Form inputs | [#] | | |
| Cards | [#] | | |
| Navigation | [#] | | |
| Modals/dialogs | [#] | | |
| Tables | [#] | | |
| Icons | [#] | | |
| Badges/tags | [#] | | |
| Loading states | [#] | | |
| Empty states | [#] | | |
| Error states | [#] | | |
| Tooltips | [#] | | |

---

## 3. Consistency Score

Rate each area on a 1-5 scale:

| Area | Score (1-5) | Evidence |
|------|------------|----------|
| Color consistency | [#] | [Brief note] |
| Typography consistency | [#] | [Brief note] |
| Spacing consistency | [#] | [Brief note] |
| Component consistency | [#] | [Brief note] |
| Interaction consistency | [#] | [Brief note] |
| Naming consistency (code) | [#] | [Brief note] |
| **Overall** | **[Average]** | |

**Scale:**
- 1: Chaotic — no discernible pattern
- 2: Emerging — some patterns, many exceptions
- 3: Partial — patterns exist but aren't universally applied
- 4: Consistent — clear system with minor deviations
- 5: Systematic — fully governed, deviations are intentional and documented

---

## 4. Accessibility Snapshot

| Check | Pass/Fail | Count of Issues |
|-------|-----------|----------------|
| Color contrast (text) | | |
| Color contrast (UI components) | | |
| Keyboard navigation | | |
| Focus indicators visible | | |
| ARIA roles present | | |
| Touch targets ≥ 24px | | |
| Alt text on images | | |
| Color not sole indicator | | |

---

## 5. Findings Summary

### Top Inconsistencies (Ranked by Impact)

| # | Finding | Severity | Affected Areas | Recommendation |
|---|---------|----------|---------------|----------------|
| 1 | [Description] | [High/Medium/Low] | [Where] | [Action] |
| 2 | [Description] | [High/Medium/Low] | [Where] | [Action] |
| 3 | [Description] | [High/Medium/Low] | [Where] | [Action] |
| 4 | [Description] | [High/Medium/Low] | [Where] | [Action] |
| 5 | [Description] | [High/Medium/Low] | [Where] | [Action] |

### Quick Wins (High Impact, Low Effort)

1. [Action item]
2. [Action item]
3. [Action item]

### Foundational Investments (High Impact, High Effort)

1. [Action item]
2. [Action item]
3. [Action item]

---

## 6. Recommended Roadmap

### Phase 1: Foundation (Weeks 1-4)
- [ ] Define design tokens (colors, typography, spacing)
- [ ] Document top 10 most-used components
- [ ] Establish naming conventions
- [ ] Set up pattern library tooling

### Phase 2: Core System (Weeks 5-12)
- [ ] Build and publish core component library
- [ ] Migrate first product area to use system components
- [ ] Establish governance and contribution process
- [ ] Create onboarding guide for consumers

### Phase 3: Scale (Weeks 13+)
- [ ] Expand component coverage to 80%+
- [ ] Add theming support (dark mode, brand variants)
- [ ] Measure and publish adoption metrics
- [ ] Establish quarterly audit cadence

---

## 7. Appendix

### Screenshots

[Include grouped screenshots from the interface inventory — organize by component category]

### Participants

| Name | Role | Contribution |
|------|------|-------------|
| [Name] | [Role] | [What they audited] |
