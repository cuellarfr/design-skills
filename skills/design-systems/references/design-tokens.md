# Design Tokens

Design tokens are the single source of truth for design decisions — named, platform-agnostic values that replace hardcoded colors, sizes, and styles throughout a product.

---

## Why Tokens Matter

Without tokens:
- A developer picks `#2563EB` from a mock-up. Another developer picks `#2564EA` from a different mock-up. Neither knows which is "right"
- Changing the brand color requires finding and replacing hex codes across thousands of files
- Dark mode, high contrast, and white-label variants each require a separate codebase

With tokens:
- Everyone references `color-action-primary`. The value is defined once
- Changing the brand color means updating one token. Every product updates automatically
- Themes swap token values. Components don't change

---

## Three-Tier Token Architecture

### Tier 1: Global (Reference) Tokens

The raw palette — every available value in the system. These are the building blocks, not meant for direct use in components.

```json
{
  "color": {
    "blue-50":  { "value": "#EFF6FF" },
    "blue-100": { "value": "#DBEAFE" },
    "blue-500": { "value": "#3B82F6" },
    "blue-600": { "value": "#2563EB" },
    "blue-900": { "value": "#1E3A5A" },
    "gray-50":  { "value": "#F9FAFB" },
    "gray-900": { "value": "#111827" }
  },
  "space": {
    "0": { "value": "0" },
    "1": { "value": "4px" },
    "2": { "value": "8px" },
    "3": { "value": "12px" },
    "4": { "value": "16px" },
    "6": { "value": "24px" },
    "8": { "value": "32px" },
    "12": { "value": "48px" },
    "16": { "value": "64px" }
  },
  "font-size": {
    "xs":  { "value": "12px" },
    "sm":  { "value": "14px" },
    "md":  { "value": "16px" },
    "lg":  { "value": "18px" },
    "xl":  { "value": "20px" },
    "2xl": { "value": "24px" },
    "3xl": { "value": "30px" },
    "4xl": { "value": "36px" }
  }
}
```

### Tier 2: Semantic (Alias) Tokens

Purpose-mapped tokens that reference globals. These communicate **intent**, not value.

```json
{
  "color-action-primary":     { "value": "{color.blue-600}" },
  "color-action-primary-hover": { "value": "{color.blue-500}" },
  "color-background-default": { "value": "{color.gray-50}" },
  "color-background-surface":  { "value": "#FFFFFF" },
  "color-text-primary":       { "value": "{color.gray-900}" },
  "color-text-secondary":     { "value": "{color.gray-600}" },
  "color-text-on-action":     { "value": "#FFFFFF" },
  "color-border-default":     { "value": "{color.gray-200}" },
  "color-feedback-error":     { "value": "{color.red-600}" },
  "color-feedback-success":   { "value": "{color.green-600}" },
  "color-feedback-warning":   { "value": "{color.yellow-500}" },
  "space-inline-sm":          { "value": "{space.2}" },
  "space-inline-md":          { "value": "{space.4}" },
  "space-stack-sm":           { "value": "{space.2}" },
  "space-stack-md":           { "value": "{space.4}" },
  "space-stack-lg":           { "value": "{space.8}" },
  "font-size-body":           { "value": "{font-size.md}" },
  "font-size-heading":        { "value": "{font-size.2xl}" }
}
```

### Tier 3: Component Tokens

Component-specific tokens referencing semantic tokens. These are optional — use them when a component needs to deviate from semantic defaults or when theming complexity justifies the indirection.

```json
{
  "button-bg-primary":        { "value": "{color-action-primary}" },
  "button-bg-primary-hover":  { "value": "{color-action-primary-hover}" },
  "button-text-primary":      { "value": "{color-text-on-action}" },
  "button-padding-x":         { "value": "{space-inline-md}" },
  "button-padding-y":         { "value": "{space-inline-sm}" },
  "button-border-radius":     { "value": "{border-radius.md}" },
  "card-bg":                  { "value": "{color-background-surface}" },
  "card-padding":             { "value": "{space-stack-md}" },
  "card-border":              { "value": "{color-border-default}" },
  "card-border-radius":       { "value": "{border-radius.lg}" }
}
```

---

## Naming Convention

### Structure

```
{category}-{property}-{element}-{variant}-{state}
```

Not every segment is required. Use only what's needed:

| Segment | Values | Examples |
|---------|--------|----------|
| **Category** | `color`, `space`, `font`, `border`, `shadow`, `motion`, `size`, `opacity` | `color-...`, `space-...` |
| **Property** | `background`, `text`, `border`, `padding`, `margin`, `size`, `weight`, `radius`, `duration` | `color-background-...` |
| **Element** | `surface`, `action`, `input`, `heading`, `body`, `caption` | `color-background-surface` |
| **Variant** | `primary`, `secondary`, `tertiary`, `inverse`, `subtle`, `bold` | `color-action-primary` |
| **State** | `default`, `hover`, `active`, `focus`, `disabled`, `error` | `color-action-primary-hover` |

### Naming Rules

1. **Use kebab-case**: `color-text-primary`, not `colorTextPrimary` (token names are platform-agnostic; case conversion happens at build time)
2. **Describe purpose, not value**: `color-feedback-error`, not `color-red-600`
3. **Be predictable**: Anyone should be able to guess a token name. If `color-action-primary` exists, `color-action-secondary` should too
4. **Avoid abbreviations**: `background` not `bg`, `typography` not `typo` — clarity over brevity in token names (code aliases can abbreviate)
5. **Match scales consistently**: If spacing uses t-shirt sizes (sm, md, lg), typography should too — don't mix t-shirt sizes with numbers

---

## W3C Design Tokens Format

The W3C Design Tokens Community Group is standardizing token format. Key aspects:

### File Structure
```json
{
  "$name": "My Design System",
  "$description": "Design tokens for...",
  "color": {
    "primary": {
      "$type": "color",
      "$value": "#2563EB",
      "$description": "Primary brand color"
    }
  }
}
```

### Supported Types
- `color` — CSS color values
- `dimension` — Sizes with units (px, rem, em)
- `fontFamily` — Font stack
- `fontWeight` — Numeric weight (100-900)
- `duration` — Time values (ms, s)
- `cubicBezier` — Easing curves [x1, y1, x2, y2]
- `number` — Unitless numbers (line-height, opacity)
- `shadow` — Box shadow definitions
- `border` — Border shorthand
- `transition` — Combined duration + delay + easing
- `gradient` — Color gradients
- `typography` — Composite type (family + size + weight + line-height + letter-spacing)

### Aliases
```json
{
  "action-primary": {
    "$type": "color",
    "$value": "{color.primary}"
  }
}
```

Curly braces `{}` denote references to other tokens — this is the standard alias syntax.

---

## Theming with Tokens

Themes work by swapping token values at the semantic tier while keeping component code identical.

### Light/Dark Example

```json
// light.tokens.json
{
  "color-background-default": { "value": "#FFFFFF" },
  "color-text-primary":       { "value": "#111827" },
  "color-border-default":     { "value": "#E5E7EB" }
}

// dark.tokens.json
{
  "color-background-default": { "value": "#1F2937" },
  "color-text-primary":       { "value": "#F9FAFB" },
  "color-border-default":     { "value": "#374151" }
}
```

Components reference `color-background-default`. They never know which theme is active.

### Theme Checklist

- [ ] Contrast ratios meet WCAG AA (4.5:1 for text, 3:1 for large text/UI) in **every** theme
- [ ] Semantic colors (error, success, warning) are distinguishable in every theme
- [ ] Shadows and elevation are visible in every theme (dark mode may need reduced or inverted shadows)
- [ ] Images and illustrations adapt or remain legible across themes
- [ ] Focus indicators are visible against every background color in every theme
- [ ] No information conveyed by color alone (WCAG 1.4.1)

---

## Platform Delivery

Tokens are authored once and transformed for each platform:

| Platform | Output Format | Tool |
|----------|--------------|------|
| Web (CSS) | CSS custom properties: `--color-action-primary: #2563EB` | Style Dictionary, Tokens Studio |
| Web (JS) | ES module: `export const colorActionPrimary = '#2563EB'` | Style Dictionary |
| iOS | Swift asset catalog or `UIColor` extension | Style Dictionary |
| Android | XML resources or Compose theme | Style Dictionary |
| Figma | Figma Variables (synced via Tokens Studio or API) | Tokens Studio, Figma Plugin API |

### Build Pipeline

```
tokens.json (source of truth)
    ↓ Style Dictionary / token transformer
    ├── css/variables.css
    ├── js/tokens.js
    ├── ios/Colors.swift
    ├── android/colors.xml
    └── figma/ (via Tokens Studio sync)
```

**Critical rule**: The token JSON file is the single source of truth. All platform outputs are generated artifacts. Never edit generated files directly.

---

## Token Audit Checklist

When reviewing an existing token system:

- [ ] Every raw value in component code traces back to a token
- [ ] No orphaned tokens (defined but never used)
- [ ] No duplicate semantic tokens pointing to the same value (consolidate)
- [ ] Naming is consistent and predictable across all categories
- [ ] Every color token meets contrast requirements in all themes
- [ ] Spacing scale is consistent (base unit × multiplier, no arbitrary gaps)
- [ ] Typography scale follows a mathematical progression (1.25x, 1.333x, or 1.5x ratio)
- [ ] Token deprecation process exists for removing old tokens
- [ ] Token documentation includes purpose, not just value
