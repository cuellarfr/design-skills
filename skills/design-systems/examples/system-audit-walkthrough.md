# System Audit Walkthrough

End-to-end audit of a fictional e-commerce product — "ShopWell" — revealing inconsistencies and producing a consolidation plan.

---

## Context

**Product:** ShopWell — a mid-size e-commerce platform with ~60 screens
**Team:** 4 designers, 8 front-end developers, no dedicated design system team
**Maturity:** Level 2 (Emerging) — some shared Figma styles, a loose CSS variables file, no component library
**Trigger:** New VP of Design joined and noticed visual inconsistencies across the product. Development velocity is declining because each feature reinvents common patterns.

---

## Step 1: Assemble the Team

**Participants:**
- 2 designers (product and marketing)
- 2 front-end developers (customer-facing and admin)
- 1 product manager
- 1 QA engineer

**Setup:** A Miro board with sections for each UI pattern category. Each participant gets 45 minutes to screenshot patterns from their area of the product.

---

## Step 2: Screenshot Exercise

Each participant captures every unique instance of each pattern category from the live product.

---

## Step 3: Present Findings

### Buttons — 14 unique styles found

| Variant | Count | Differences |
|---------|-------|------------|
| Filled blue | 4 | Different blues: #2563EB, #3B82F6, #1D4ED8, #2557D6 |
| Filled green | 2 | Used for "Add to cart" and "Confirm" — different greens |
| Outlined | 3 | Different border widths (1px, 1.5px, 2px) and radii (4px, 6px, 8px) |
| Ghost/text | 3 | Different text colors and hover treatments |
| Icon-only | 2 | Different sizes (32px, 40px), no consistent padding |

**Root cause:** No shared button component. Each team copied styles from whichever screen they looked at most recently.

**Recommendation:** Consolidate to 4 button variants: Primary (filled), Secondary (outlined), Tertiary (ghost), Icon-only. One color system, one border-radius, one size scale (sm/md/lg).

### Colors — 47 unique color values found

| Category | Unique Values | Should Be |
|----------|--------------|-----------|
| Blues (brand) | 8 | 1 ramp of 10 |
| Grays | 12 | 1 ramp of 10 |
| Reds (error) | 4 | 1 ramp of 10 |
| Greens (success) | 3 | 1 ramp of 10 |
| Other | 20 | Eliminated or mapped to semantic tokens |

**Contrast violations:** 11 text-on-background combinations fail WCAG AA (4.5:1). Most are gray text on light gray backgrounds.

**Recommendation:** Define a token architecture. 4 color ramps (brand, neutral, error, success), semantic aliases for every use case, and contrast-check every pairing.

### Typography — 9 font sizes, no scale

| Found | Sizes in Use |
|-------|-------------|
| Headings | 36px, 32px, 28px, 24px, 22px, 20px |
| Body | 16px, 14px, 13px |
| Captions | 12px, 11px |

The sizes don't follow any mathematical progression. 22px and 28px are used inconsistently — sometimes as h2, sometimes as h3.

**Recommendation:** Adopt a 1.25 scale (Major Third) from a 16px base: 12, 14, 16, 20, 25, 31, 39. Map each to a semantic token (body, heading-sm, heading-md, etc.). Eliminate 11px, 13px, 22px, 28px, 32px, 36px.

### Spacing — No system detected

Analysis of padding and margin values across 20 screens:
- 37 unique spacing values ranging from 2px to 96px
- No base unit pattern
- Same component (product card) has 12px padding on the homepage and 16px on the category page

**Recommendation:** Adopt an 8px base with half-step (4px) for tight spacing: 0, 4, 8, 12, 16, 24, 32, 48, 64.

### Cards — 7 distinct implementations

| Where | Image | Title Size | Padding | Border | Shadow |
|-------|-------|-----------|---------|--------|--------|
| Homepage featured | 16:9 | 20px bold | 16px | None | Yes |
| Category grid | 1:1 | 14px semibold | 12px | 1px gray | No |
| Search results | 4:3 | 16px medium | 16px | None | Yes |
| Wishlist | 1:1 | 14px regular | 8px | 1px gray | No |
| Related products | 16:9 | 14px semibold | 12px | None | Subtle |
| Recently viewed | 1:1 | 12px regular | 8px | None | No |
| Admin product list | None | 14px medium | 12px | 1px | No |

**Root cause:** Each feature was built by a different developer referencing a different Figma file from a different point in time.

**Recommendation:** Define 3 card variants: Default (image + content, standard padding), Compact (smaller, dense lists), and List (horizontal, text-dominant for admin). One image ratio per variant. One token set for padding, typography, and border.

---

## Step 4: Scoring

| Area | Score (1-5) | Evidence |
|------|------------|----------|
| Color consistency | 2 | 47 unique values, 11 contrast failures |
| Typography consistency | 2 | 9+ sizes with no scale, inconsistent heading hierarchy |
| Spacing consistency | 1 | 37 unique values, no base unit |
| Component consistency | 2 | 7 card variants, 14 button styles |
| Interaction consistency | 3 | Hover states exist but vary in timing and treatment |
| Naming consistency (code) | 2 | Mix of `.btn-primary`, `.button-main`, `.cta-blue` |
| **Overall** | **2.0** | Level 2 — Emerging |

---

## Step 5: Consolidation Plan

### Phase 1: Tokens (Weeks 1-3)

**Goal:** Single source of truth for all design values

| Deliverable | Details |
|-------------|---------|
| Color tokens | 4 ramps (brand, neutral, error, success) + semantic aliases |
| Typography tokens | 7-size scale (1.25 ratio), 2 font families, 3 weights |
| Spacing tokens | 9-step scale (4px half-step, 8px base) |
| Border/shadow tokens | 3 radii, 4 shadows |
| Motion tokens | 3 durations, 3 easing curves |

**Success metric:** Zero raw values in new code. All values reference tokens.

### Phase 2: Core Components (Weeks 4-8)

**Goal:** 15 most-used components specified, built, and documented

Priority order (by usage frequency from analytics):
1. Button (4 variants)
2. Input (text, select, checkbox, radio, toggle)
3. Card (3 variants)
4. Badge/Tag
5. Modal
6. Navigation (header, sidebar)
7. Table
8. Tabs
9. Tooltip
10. Alert/Banner
11. Avatar
12. Pagination
13. Breadcrumb
14. Empty state
15. Loading skeleton

**Success metric:** First product area fully migrated to system components.

### Phase 3: Governance (Weeks 9-12)

**Goal:** Sustainable process for maintaining and evolving the system

| Deliverable | Details |
|-------------|---------|
| Contribution guidelines | How to propose, review, and publish patterns |
| Naming conventions | Documented and enforced via linter |
| Versioning policy | Semver with changelog |
| Communication plan | Slack channel, monthly demos, release notes |
| Adoption dashboard | Component usage metrics |

**Success metric:** First external contribution (from a product team, not the core team) accepted and published.

---

## Outcome

The audit Miro board became the single most effective artifact for securing executive buy-in. Showing 14 button styles side-by-side made the case that a style guide could not. The team received approval for a 20% time allocation (1 designer + 1 developer, 1 day per week) to begin Phase 1.

**Key insight:** The audit didn't just reveal inconsistencies — it revealed that the team had been doing redundant work for months. The time saved by consolidating would more than pay for the system investment.
