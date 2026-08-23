# Pattern Documentation

How to write comprehensive pattern library entries that serve designers, developers, content strategists, and product managers.

---

## Anatomy of a Pattern Entry

Every pattern in the library should include these sections. Incomplete documentation leads to inconsistent implementation.

### 1. Header

```
Name:        [Context-agnostic name]
Purpose:     [One sentence: what user need does this serve?]
Status:      [Draft | Beta | Stable | Deprecated]
Version:     [Semantic version: 1.0.0]
Last updated: [Date]
Owner:       [Person or team responsible]
```

### 2. Description

2-3 sentences explaining:
- What the pattern is
- When to use it
- What makes it distinct from similar patterns

**Example:**
> A Card is a contained unit of content that acts as an entry point to more detailed information. Use Cards when presenting a collection of related items that users browse and select from. Cards differ from List Items in that they emphasize visual content and support richer layouts.

### 3. Visual Example

Show the rendered component in its default state. Include:
- Live, interactive instance (not a static screenshot — screenshots go stale)
- Light and dark theme variants
- Responsive breakpoints (mobile, tablet, desktop)

### 4. Anatomy Diagram

Name every sub-part of the component. Use numbered callouts:

```
┌──────────────────────────┐
│ ┌──────────────────────┐ │
│ │    1. Image           │ │
│ └──────────────────────┘ │
│  2. Category tag          │
│  3. Title                 │
│  4. Description           │
│  5. Metadata (date, read  │
│     time, author)         │
│  ┌─────────┐             │
│  │ 6. CTA  │             │
│  └─────────┘             │
└──────────────────────────┘
```

Every sub-part should reference which atom or molecule it corresponds to in the system.

### 5. Variants

Document each legitimate variant:

| Variant | Visual | When to Use | When NOT to Use |
|---------|--------|-------------|-----------------|
| **Default** | Image + title + description + CTA | General browsing collections | When items have no visual content |
| **Compact** | Title + description only | Dense lists, dashboards, sidebars | Primary browsing experiences |
| **Media** | Large image + overlay title | Image-heavy content (galleries, portfolios) | Data-heavy or text-heavy content |
| **Horizontal** | Image left, content right | Wide containers, featured items | Narrow columns, mobile |

**Maximum 5 variants.** If you need more, the pattern likely needs to be split into distinct patterns with different purposes.

### 6. States

Document every possible state:

| State | Appearance | Trigger | Notes |
|-------|-----------|---------|-------|
| **Default** | Neutral background, standard border | Page load | Primary visual treatment |
| **Hover** | Subtle elevation increase, cursor change | Mouse enter | Interaction affordance. Touch devices skip this |
| **Active/Pressed** | Slight scale reduction (98%) | Mouse down / touch start | Tactile feedback |
| **Focus** | Visible focus ring (2px, offset 2px) | Keyboard tab | Must meet 3:1 contrast against adjacent colors |
| **Selected** | Accent border or background tint | Click / Enter key | For selectable card patterns |
| **Disabled** | 40% opacity, no pointer events | Programmatic | Include `aria-disabled="true"` |
| **Loading** | Skeleton placeholder (pulse animation) | Data fetching | Match layout dimensions exactly |
| **Empty** | Illustration + message + action | Zero data | Never show an empty card — always guide the user |
| **Error** | Error border + inline message | Failed data load | Offer retry action |

### 7. Content Guidelines

| Element | Min | Max | Truncation | Notes |
|---------|-----|-----|------------|-------|
| **Title** | 2 words | 60 characters | Single-line ellipsis | Sentence case. No periods |
| **Description** | 10 characters | 120 characters | 2-line clamp | First sentence should be self-sufficient |
| **Image** | 16:9 ratio | 16:9 ratio | Object-fit: cover | Provide alt text. Decorative → `alt=""` |
| **CTA text** | 1 word | 3 words | Never truncate | Action verb: "Read more," "View details" |

### 8. Behavior

**Interaction rules:**
- Entire card is clickable (not just the CTA) — use `<a>` wrapping or `role="link"`
- If card contains multiple actions, only the primary action activates on card click
- Secondary actions (bookmark, share) are scoped — clicking them does NOT trigger card navigation
- Hover animation: 200ms ease-out elevation transition
- Keyboard: Tab to focus → Enter to activate → Tab to next card

**Responsive behavior:**
- Desktop (>1024px): 3-4 column grid, 24px gap
- Tablet (768-1024px): 2 column grid, 16px gap
- Mobile (<768px): Single column, full width, 12px gap
- Card aspect ratio remains fixed. Content reflows within

### 9. Accessibility Requirements

| Requirement | Implementation | WCAG |
|-------------|---------------|------|
| **Semantic markup** | Use `<article>` or `role="article"` for each card | 1.3.1 |
| **Heading hierarchy** | Card title should be a heading element at the appropriate level | 1.3.1 |
| **Link purpose** | Link text or `aria-label` describes destination | 2.4.4 |
| **Focus visible** | 2px focus ring, 3:1 contrast minimum | 2.4.7, 2.4.11 |
| **Touch target** | Minimum 24x24px for interactive elements within cards | 2.5.8 |
| **Color independence** | Status/category not conveyed by color alone | 1.4.1 |
| **Text contrast** | 4.5:1 for body text, 3:1 for large text (>= 18px or >= 14px bold) | 1.4.3 |
| **Reduced motion** | Respect `prefers-reduced-motion` — disable hover elevation, transitions | 2.3.3 |
| **Screen reader** | Cards read as: "[Title]. [Description]. [Category]. Link." | 4.1.2 |

### 10. Design Tokens Used

List every token the component references:

```
Background:    color-background-surface
Border:        color-border-default
Title:         color-text-primary, font-size-heading-sm, font-weight-semibold
Description:   color-text-secondary, font-size-body
Padding:       space-stack-md (vertical), space-inline-md (horizontal)
Border radius: border-radius-lg
Shadow:        shadow-sm (default), shadow-md (hover)
Transition:    motion-duration-fast, motion-easing-standard
```

### 11. Code Examples

Provide implementation in the project's primary framework:

```jsx
// React example
<Card
  image={{ src: "/photo.jpg", alt: "Description" }}
  category="Design"
  title="Card Title"
  description="Brief description of the content."
  href="/article/123"
  metadata={{ date: "Mar 15", readTime: "5 min" }}
/>
```

Include:
- Default usage
- Each variant
- With and without optional props
- Accessibility-specific props (aria-label, role overrides)

### 12. Related Patterns

| Pattern | Relationship |
|---------|-------------|
| **List Item** | Use instead of Card when visual content is minimal or space is constrained |
| **Tile** | Similar but typically interactive (toggle, select) rather than navigational |
| **Hero** | Use instead when a single item needs prominent placement |
| **Modal** | Cards link to detail pages; Modals show detail inline — don't combine |

---

## Documentation Quality Checklist

Before publishing a pattern entry:

- [ ] Purpose is stated in one sentence
- [ ] Anatomy diagram with named sub-parts
- [ ] All states documented (minimum: default, hover, focus, disabled, loading, empty, error)
- [ ] Content guidelines with specific character limits
- [ ] Responsive behavior at all defined breakpoints
- [ ] Accessibility requirements with WCAG references
- [ ] Design tokens listed (no raw values in component code)
- [ ] Code example for primary framework
- [ ] At least 2 related patterns listed
- [ ] Reviewed by at least one designer AND one developer

---

## Writing Style for Documentation

### Principles
1. **Show, then tell**: Lead with the visual example, then explain in text
2. **Be prescriptive**: "Use X" not "Consider X." "Maximum 60 characters" not "Keep it short"
3. **Include the negative**: "When NOT to use" is as valuable as "When to use"
4. **Write for scanning**: Tables > paragraphs. Bullets > prose. Headers every 3-5 lines
5. **Cross-disciplinary**: Avoid jargon from only one discipline. If you must use technical terms, define them

### Anti-patterns
- Screenshot-only documentation (goes stale in weeks)
- "See Figma" as a substitute for written specs (not everyone has Figma access)
- Documenting only the happy path (edge cases cause the most bugs)
- Writing documentation after launch (write it while building — it surfaces gaps)
