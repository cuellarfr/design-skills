# Component Spec Walkthrough

Specifying a Card component from purpose through accessibility — demonstrating the full spec process.

---

## Context

**System:** A B2B SaaS product's design system (Level 3 — Managed)
**Request:** Three product teams independently built card-like components. The interface inventory found 5 different card implementations. The design system team needs to define a canonical Card pattern that replaces all five.

---

## Step 1: Define the Purpose

Before looking at any visual design, answer: **what does this pattern help users do?**

Reviewing the 5 existing implementations:
1. **Dashboard widget** — Shows a metric with trend. Purpose: *Monitor a KPI at a glance*
2. **Project card** — Shows project name, status, team. Purpose: *Browse and select a project*
3. **Notification card** — Shows message and timestamp. Purpose: *Scan and act on a notification*
4. **Resource card** — Shows title, description, thumbnail. Purpose: *Browse and select a resource*
5. **User card** — Shows avatar, name, role. Purpose: *Identify and select a team member*

**Analysis:** Items 2, 4, and 5 share the same core purpose: *Present a scannable summary that acts as an entry point to more detail.* They're the same pattern.

Items 1 and 3 serve different purposes:
- The dashboard widget is a **Stat** (a molecule — label + value + trend). It doesn't navigate anywhere.
- The notification card is a **Feed Item** — it has temporal ordering, read/unread state, and inline actions. Different enough to be its own pattern.

**Decision:** Define one **Card** pattern (covers project, resource, and user cases) and two separate patterns: **Stat** and **Feed Item**.

---

## Step 2: Identify the Anatomy

Looking at the three "Card" use cases, identify every sub-part:

| Sub-part | Project Card | Resource Card | User Card | Required? |
|----------|-------------|--------------|-----------|-----------|
| Image/visual | Project icon | Thumbnail | Avatar | Optional — some cards are text-only |
| Title | Project name | Resource title | User name | **Required** |
| Description | — | Resource description | Role | Optional |
| Metadata | Status badge + team count | Type + date | Department + location | Optional |
| Action | Navigate to project | Navigate to resource | Navigate to profile | **Required** (implicit — the card is clickable) |

**Anatomy:**

```
┌──────────────────────────────┐
│ ┌──────────┐                 │
│ │ 1. Visual │  2. Title      │
│ │  (opt.)   │  3. Description│
│ └──────────┘  4. Metadata    │
│                              │
│  5. Secondary action (opt.)  │
└──────────────────────────────┘
```

Maps to the system:
1. **Visual** → Image atom or Avatar atom (slot-based — accepts either)
2. **Title** → Heading atom (heading-sm token)
3. **Description** → Text atom (body-sm token)
4. **Metadata** → Metadata molecule (icon + text pairs, badges)
5. **Secondary action** → Icon Button atom (optional slot)

---

## Step 3: Define Variants

Based on the three use cases and the anatomy, define the minimum variants:

| Variant | Visual | Layout | When to Use |
|---------|--------|--------|-------------|
| **Default** | Image/icon, top | Vertical stack | General browsing — resources, articles, products |
| **Compact** | Avatar/icon, inline left | Horizontal, single row | Dense lists — team members, sidebar items, search results |
| **Media** | Large image, full-width top | Vertical, image-dominant | Visual content — galleries, templates, portfolios |

Three variants. Each maps clearly to a use case. No overlap.

**Rejected variant:** "Horizontal card" (image left, content right) — this is the Compact variant at larger sizes. Responsive behavior handles it — no separate variant needed.

---

## Step 4: Specify States

| State | Visual Treatment | Implementation |
|-------|-----------------|----------------|
| **Default** | `shadow-sm`, `color-background-surface`, `color-border-default` | Standard render |
| **Hover** | `shadow-md`, slight scale (`transform: scale(1.01)`) | 200ms ease-out transition. Touch devices: no hover state |
| **Active** | `shadow-sm` returns, `transform: scale(0.99)` | 100ms ease-in-out |
| **Focus** | 2px focus ring, `color-border-focus`, offset 2px | Keyboard tab. Ring contrast ≥ 3:1 against card background and page background |
| **Selected** | Left border 3px `color-action-primary`, subtle background tint | For multi-select contexts (e.g., "Select projects to archive"). Add `aria-selected="true"` |
| **Disabled** | 40% opacity, no pointer events, no hover/focus | `aria-disabled="true"`. Remove from tab order |
| **Loading** | Skeleton placeholder matching layout exactly. Pulse animation | `aria-busy="true"` on the container. Skeleton height matches content height |
| **Empty** | N/A — cards are not rendered when empty. The **grid/list** shows an empty state | Empty state is the parent's responsibility, not the card's |
| **Error** | N/A — if card data fails to load, show skeleton → then error message in grid | Same as empty — error handling is at the container level |

---

## Step 5: Content Guidelines

| Element | Min | Max | Truncation | Rules |
|---------|-----|-----|------------|-------|
| **Title** | 2 words | 60 chars | Single-line ellipsis with `title` attribute for full text | Sentence case. No periods. Must be meaningful without description |
| **Description** | — | 120 chars | 2-line clamp | Optional. If present, first sentence must be self-sufficient |
| **Image** | 200×150px source min | No max (responsive) | `object-fit: cover` | Alt text required. Decorative images: `alt=""` |
| **Metadata** | 1 item | 3 items | Overflow hidden | Keep metadata scannable — icons help. No full sentences |
| **Secondary action label** | — | — | Icon-only at mobile | Tooltip on icon buttons. `aria-label` required |

---

## Step 6: Behavior Specification

### Interaction

- **Primary action:** Clicking anywhere on the card navigates to the detail page. Implemented with a wrapping `<a>` element or `role="link"` + `tabindex="0"` + click/keydown handlers
- **Secondary action:** If present (e.g., a bookmark button), clicking it does NOT trigger card navigation. Implemented as a separate `<button>` inside the card, with `event.stopPropagation()`
- **Keyboard:** Tab focuses the card → Enter activates primary action → Tab again moves to secondary action (if present) → Tab moves to next card

### Responsive Behavior

| Breakpoint | Default Variant | Compact Variant | Media Variant |
|-----------|----------------|-----------------|---------------|
| Desktop (>1024px) | 3-4 column grid, `space-6` gap | Single column list, `space-3` gap | 3 column grid, `space-6` gap |
| Tablet (768-1024px) | 2 column grid, `space-4` gap | Single column, `space-2` gap | 2 column grid, `space-4` gap |
| Mobile (<768px) | Single column, full width, `space-4` gap | Single column, `space-2` gap | Single column, full width, `space-4` gap |

### Animation

- Hover elevation: `transition: box-shadow 200ms {motion-easing-standard}, transform 200ms {motion-easing-standard}`
- `@media (prefers-reduced-motion: reduce)`: Remove transform, keep instant shadow change

---

## Step 7: Accessibility Specification

| Requirement | Implementation | WCAG | Test |
|-------------|---------------|------|------|
| Semantic container | `<article>` element | 1.3.1 | Screen reader announces "article" |
| Heading hierarchy | Title uses `<h3>` (or appropriate level for page context) | 1.3.1 | Headings list shows card titles |
| Link purpose | Card link `aria-label` includes title: `aria-label="View [Title]"` | 2.4.4 | Screen reader announces destination |
| Focus visible | 2px solid `color-border-focus`, 2px offset | 2.4.7, 2.4.11 | Visible on keyboard navigation |
| Touch target | Entire card is the touch target (well above 44x44px) | 2.5.8 | ✓ by design |
| Color independence | Status shown with badge text + color (not color alone) | 1.4.1 | Remove color → information preserved |
| Text contrast | Title: 7:1 on surface (AAA). Description: 4.5:1 on surface (AA) | 1.4.3 | Automated contrast check |
| Reduced motion | Transform removed, shadow change instant | 2.3.3 | Toggle `prefers-reduced-motion` |
| Screen reader flow | Reads: "[Title]. [Description]. [Metadata]. Link to [detail]." | 4.1.2 | VoiceOver/NVDA test |

---

## Step 8: Token Mapping

```
Card background:       color-background-surface
Card border:           color-border-default (1px, border-width-sm)
Card border radius:    border-radius-lg
Card shadow (default): shadow-sm
Card shadow (hover):   shadow-md
Card padding:          space-4 (16px)
Card gap (internal):   space-2 (8px) between sub-parts

Title color:           color-text-primary
Title font:            font-heading-sm (font-size-lg, font-weight-medium)
Description color:     color-text-secondary
Description font:      font-body-sm (font-size-sm, font-weight-regular)
Metadata color:        color-text-tertiary
Metadata font:         font-caption (font-size-xs, font-weight-regular)

Focus ring:            color-border-focus (2px, 2px offset)
Selected border:       color-action-primary (3px left border)
Selected background:   color-action-primary at 5% opacity

Hover transition:      motion-duration-normal, motion-easing-standard
Active transition:     motion-duration-fast, motion-easing-standard
```

---

## Step 9: Code Example

```jsx
// Default variant
<Card
  href="/projects/123"
  image={{ src: "/project-icon.png", alt: "" }}
  title="Website Redesign"
  description="Q2 initiative to modernize the marketing site"
  metadata={[
    { icon: "status", label: "In Progress" },
    { icon: "team", label: "5 members" }
  ]}
/>

// Compact variant
<Card
  variant="compact"
  href="/team/jane-smith"
  image={{ src: "/avatars/jane.jpg", alt: "" }}
  title="Jane Smith"
  metadata={[{ label: "Design Lead" }]}
/>

// With secondary action
<Card
  href="/resources/brand-guide"
  image={{ src: "/thumbnails/brand.png", alt: "Brand guide cover" }}
  title="Brand Guidelines v2"
  description="Updated visual identity and usage rules"
  secondaryAction={{
    icon: "bookmark",
    label: "Save for later",
    onClick: handleBookmark
  }}
/>
```

---

## Step 10: Related Patterns

| Pattern | Relationship |
|---------|-------------|
| **Stat** | Use instead of Card when displaying a single metric without navigation |
| **Feed Item** | Use instead of Card for time-ordered items with read/unread state and inline actions |
| **List Item** | Use instead of Card when visual content is minimal and space is constrained. A list item is simpler — typically text + optional icon + optional action |
| **Tile** | Use instead of Card for interactive selection (toggle, radio-like behavior) rather than navigation |
| **Modal** | Cards navigate to detail pages. Modals show detail inline. Don't put a modal trigger inside a card |

---

## Outcome

The Card specification replaced 5 ad-hoc implementations with 3 well-defined variants. The spec took 3 hours to write (1 hour purpose analysis, 1 hour spec writing, 1 hour design + dev review). Implementation took 2 days. Migration of existing card instances across the product took 2 sprints.

**Measured impact:**
- CSS reduced by ~400 lines (removed 5 bespoke card stylesheets)
- Accessibility violations in card components dropped from 8 to 0
- New features using cards now take hours instead of days to implement
- Designers reference one Figma component instead of hunting for "the right card"
