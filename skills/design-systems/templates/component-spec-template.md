# Component Specification: [Component Name]

## Header

| Field | Value |
|-------|-------|
| **Name** | [Context-agnostic name] |
| **Purpose** | [One sentence: what user need does this serve?] |
| **Status** | [Draft / Beta / Stable / Deprecated] |
| **Version** | [1.0.0] |
| **Owner** | [Person or team] |
| **Last updated** | [Date] |

---

## Description

[2-3 sentences: What is this component? When should it be used? What makes it distinct from similar patterns?]

---

## Anatomy

[Numbered diagram or description of sub-parts]

```
┌─────────────────────────┐
│  1. [Sub-part name]     │
│  2. [Sub-part name]     │
│  3. [Sub-part name]     │
│  4. [Sub-part name]     │
└─────────────────────────┘
```

| # | Sub-part | Required | Maps to |
|---|----------|----------|---------|
| 1 | [Name] | Yes / No | [Atom or molecule in the system] |
| 2 | [Name] | Yes / No | [Atom or molecule in the system] |
| 3 | [Name] | Yes / No | [Atom or molecule in the system] |
| 4 | [Name] | Yes / No | [Atom or molecule in the system] |

---

## Variants

| Variant | When to Use | When NOT to Use |
|---------|-------------|-----------------|
| **Default** | [Context] | [Context] |
| **[Variant 2]** | [Context] | [Context] |
| **[Variant 3]** | [Context] | [Context] |

Maximum 5 variants. If more are needed, consider splitting into separate patterns.

---

## States

| State | Appearance | Trigger | ARIA |
|-------|-----------|---------|------|
| **Default** | [Description] | Page load | — |
| **Hover** | [Description] | Mouse enter | — |
| **Active** | [Description] | Mouse down | — |
| **Focus** | [Focus ring spec] | Keyboard tab | — |
| **Disabled** | [Description] | Programmatic | `aria-disabled="true"` |
| **Loading** | [Skeleton or spinner] | Data fetch | `aria-busy="true"` |
| **Empty** | [Empty state design] | Zero data | — |
| **Error** | [Error treatment] | Validation / server | `aria-invalid="true"` |

---

## Content Guidelines

| Element | Min | Max | Truncation | Rules |
|---------|-----|-----|------------|-------|
| [Element 1] | [Min length] | [Max length] | [Behavior] | [Case, punctuation, etc.] |
| [Element 2] | [Min length] | [Max length] | [Behavior] | [Case, punctuation, etc.] |
| [Element 3] | [Min length] | [Max length] | [Behavior] | [Case, punctuation, etc.] |

---

## Behavior

### Interaction Rules
- [What happens on click/tap]
- [What happens on keyboard interaction (Enter, Space, Escape, Arrow keys)]
- [Animation details: duration, easing, what moves]

### Responsive Behavior

| Breakpoint | Layout Change |
|-----------|---------------|
| Desktop (>1024px) | [Description] |
| Tablet (768-1024px) | [Description] |
| Mobile (<768px) | [Description] |

---

## Accessibility

| Requirement | Implementation | WCAG |
|-------------|---------------|------|
| Semantic role | [Element or ARIA role] | 1.3.1 |
| Keyboard navigation | [Tab order, key bindings] | 2.1.1 |
| Focus visible | [Focus ring spec] | 2.4.7 |
| Screen reader | [What is announced] | 4.1.2 |
| Color independence | [How meaning is conveyed without color] | 1.4.1 |
| Text contrast | [Ratio against background] | 1.4.3 |
| Touch target | [Minimum size] | 2.5.8 |
| Reduced motion | [Alternative for prefers-reduced-motion] | 2.3.3 |

---

## Design Tokens

```
[Category]:    [token-name]
[Category]:    [token-name]
[Category]:    [token-name]
[Category]:    [token-name]
```

No raw hex codes, pixel values, or magic numbers. Every value must reference a token.

---

## Code Example

```jsx
// Default usage
<[ComponentName]
  [prop]="[value]"
  [prop]="[value]"
/>

// With optional props
<[ComponentName]
  [prop]="[value]"
  [optionalProp]="[value]"
  [optionalProp]="[value]"
/>
```

---

## Related Patterns

| Pattern | Relationship |
|---------|-------------|
| [Pattern name] | [Use instead when...] |
| [Pattern name] | [Often used together with...] |
| [Pattern name] | [Easily confused with — key difference is...] |

---

## Changelog

| Version | Date | Change |
|---------|------|--------|
| 1.0.0 | [Date] | Initial release |
