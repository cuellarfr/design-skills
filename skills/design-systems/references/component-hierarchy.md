# Component Hierarchy

Detailed breakdown of the five levels of UI granularity from Brad Frost's Atomic Design, adapted for practical design system work.

---

## Atoms

### Definition
The smallest UI elements that can't be broken down further without losing their function. In web terms: HTML elements. In design system terms: base components and design tokens.

### Identifying Atoms
An element is an atom if:
- It has a single, indivisible purpose
- Removing any part of it makes it non-functional
- It appears as a building block inside multiple larger patterns

### Catalog of Common Atoms

| Category | Atoms |
|----------|-------|
| **Text** | Heading (h1-h6), paragraph, label, caption, helper text, link |
| **Controls** | Button, icon button, toggle, checkbox, radio button, slider |
| **Inputs** | Text input, textarea, select, date picker, file upload |
| **Media** | Image, avatar, icon, logo, video thumbnail |
| **Indicators** | Badge, tag, tooltip, progress bar, spinner, divider |
| **Tokens** | Colors, font families, font sizes, spacing values, shadows, border radii, animation durations |

### Atom Documentation Focus
- Every state: default, hover, active, focus, disabled
- Design token references (never raw values)
- Accessibility: minimum touch target 44x44px (AAA) or 24x24px (AA), contrast ratios, ARIA attributes
- Content constraints: min/max characters for text atoms

---

## Molecules

### Definition
Simple groups of atoms functioning together as a unit. A molecule does **one thing well**. It is portable and reusable across contexts.

### Identifying Molecules
An element is a molecule if:
- It combines 2-5 atoms into a functional unit
- It has a single, clear purpose
- It can be lifted out of its current context and placed elsewhere without modification

### Common Molecules

| Molecule | Atoms Composed | Purpose |
|----------|---------------|---------|
| **Search form** | Label + text input + button | Allow users to search content |
| **Form field** | Label + input + helper text + error message | Collect a single piece of user data |
| **Media object** | Image/avatar + text block | Display content with a visual anchor |
| **Stat** | Label + value + trend indicator | Display a single metric |
| **Nav item** | Icon + label + badge (optional) | Represent a navigation destination |
| **List item** | Checkbox/radio + label + description | Present a selectable option |

### Molecule Design Principles
1. **Do one thing**: If a molecule serves two purposes, split it
2. **Self-contained data**: A molecule should make sense with its own content — don't rely on surrounding context
3. **Minimal variants**: 1-3 variants maximum. More signals it's becoming an organism
4. **Consistent internal spacing**: Use the same spacing tokens within a molecule regardless of where it appears

---

## Organisms

### Definition
Relatively complex UI components made of groups of molecules and atoms. Organisms form **distinct sections** of an interface. They give the page its shape and personality.

### Identifying Organisms
An element is an organism if:
- It combines multiple molecules (and possibly atoms) into a section
- It serves a broader function than any single molecule
- It often represents a recognizable "section" of a page (header, sidebar, content area)

### Common Organisms

| Organism | Composed Of | Purpose |
|----------|------------|---------|
| **Site header** | Logo (atom) + nav items (molecules) + search form (molecule) + user menu (molecule) | Global navigation and identity |
| **Product card** | Image (atom) + title (atom) + price (atom) + rating (molecule) + action button (atom) | Summarize a product for browsing |
| **Comment thread** | Multiple media objects (molecules) + form field (molecule) + button (atom) | Enable discussion |
| **Data table** | Table header (molecule) + table rows (molecules) + pagination (molecule) + filters (molecules) | Display and manipulate structured data |
| **Hero section** | Heading (atom) + paragraph (atom) + CTA button (atom) + image (atom) | Introduce key content or action |
| **Footer** | Nav items (molecules) + logo (atom) + social links (atoms) + legal text (atoms) | Secondary navigation and legal |

### Organism Design Principles
1. **Composition over inheritance**: Build organisms by composing molecules, not by extending them
2. **Slot-based flexibility**: Define which molecules can occupy which positions. A card organism might accept any molecule in its "action" slot
3. **Context-agnostic naming**: "Card" not "Product card." The same card organism might display products, articles, or team members
4. **Responsive behavior**: Organisms are where layout shifts typically occur — stack, reflow, hide/show at breakpoints

---

## Templates

### Definition
Page-level structures that arrange organisms into a layout. Templates use **placeholder content** to articulate the underlying structure without committing to specific data.

### Purpose in the System
Templates answer: "How do organisms relate to each other on a page?" They define:
- Content hierarchy and reading order
- Grid and layout structure
- Which organisms are required vs. optional
- Responsive layout behavior (how the arrangement changes across breakpoints)

### Template Documentation

| Field | What to Document |
|-------|-----------------|
| **Layout grid** | Columns, gutters, margins, max-width |
| **Required organisms** | What must be present for the template to function |
| **Optional organisms** | What can be added or removed |
| **Content slots** | Named areas where organisms are placed |
| **Responsive behavior** | Layout changes at each breakpoint |
| **Scroll behavior** | Fixed elements, sticky headers, infinite scroll |

### Common Templates
- Dashboard (sidebar + header + content grid + detail panel)
- Settings (navigation + form sections + save bar)
- Article/blog (header + hero + body + sidebar + related content + footer)
- Search results (search bar + filters + results grid/list + pagination)
- Checkout flow (stepper + form sections + order summary + actions)

---

## Pages

### Definition
Specific instances of templates filled with **real, representative content**. Pages are the highest fidelity view and the ultimate test of the system.

### Why Pages Matter
Pages expose problems that templates and components hide:
- What happens when a title is 5 words vs. 50 words?
- What happens when the user has no avatar, no activity, no data?
- What about internationalization — does the layout hold with German (30% longer) or Japanese text?
- What about the first-time user vs. the power user with 500 items?

### Page Testing Checklist

- [ ] **Happy path**: Typical content, typical user — the baseline
- [ ] **Empty state**: No data, first-time user, zero results
- [ ] **Overflow**: Maximum content length in every field
- [ ] **Minimal**: Minimum required content only
- [ ] **Error state**: Validation failures, server errors, offline
- [ ] **Edge cases**: One item, 1000 items, special characters, RTL text
- [ ] **Accessibility**: Screen reader flow, keyboard navigation, zoom to 200%
- [ ] **Responsive**: Every defined breakpoint + in-between sizes

---

## Hierarchy Decision Guide

When classifying a new element:

```
Is it a single, indivisible UI element?
  → Yes: ATOM

Is it a simple group (2-5 atoms) with one purpose?
  → Yes: MOLECULE

Is it a complex section combining molecules?
  → Yes: ORGANISM

Is it a page-level layout with placeholder content?
  → Yes: TEMPLATE

Is it a template with real content for testing?
  → Yes: PAGE
```

**When classification is ambiguous**: Default to the simpler level. A "molecule" that grows complex should be promoted to organism. An "organism" that's really just two atoms should be demoted to molecule. Complexity should be earned, not assumed.
