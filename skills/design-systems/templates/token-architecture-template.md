# Token Architecture: [System Name]

**Version:** [1.0.0]
**Last updated:** [Date]
**Owner:** [Person or team]

---

## Token Tiers

This system uses a three-tier token architecture:

| Tier | Purpose | Who References |
|------|---------|---------------|
| **Global** | Raw palette of all available values | Semantic tokens only — never used directly in components |
| **Semantic** | Purpose-mapped tokens | Components and layouts |
| **Component** | Component-specific overrides | Individual components (optional tier) |

---

## Naming Convention

```
{category}-{property}-{element}-{variant}-{state}
```

| Segment | Required | Values |
|---------|----------|--------|
| Category | Yes | `color`, `space`, `font`, `border`, `shadow`, `motion`, `size`, `opacity` |
| Property | Usually | `background`, `text`, `border`, `padding`, `size`, `weight`, `radius`, `duration` |
| Element | Sometimes | `surface`, `action`, `input`, `heading`, `body` |
| Variant | Sometimes | `primary`, `secondary`, `tertiary`, `inverse`, `subtle` |
| State | Sometimes | `default`, `hover`, `active`, `focus`, `disabled`, `error` |

---

## Color Tokens

### Global Colors

| Token | Value | Notes |
|-------|-------|-------|
| **Brand** | | |
| `[brand]-50` | [#hex] | Lightest tint |
| `[brand]-100` | [#hex] | |
| `[brand]-200` | [#hex] | |
| `[brand]-300` | [#hex] | |
| `[brand]-400` | [#hex] | |
| `[brand]-500` | [#hex] | Base |
| `[brand]-600` | [#hex] | |
| `[brand]-700` | [#hex] | |
| `[brand]-800` | [#hex] | |
| `[brand]-900` | [#hex] | Darkest shade |
| **Neutral** | | |
| `gray-50` | [#hex] | |
| `gray-100` | [#hex] | |
| `gray-200` | [#hex] | |
| `gray-300` | [#hex] | |
| `gray-400` | [#hex] | |
| `gray-500` | [#hex] | |
| `gray-600` | [#hex] | |
| `gray-700` | [#hex] | |
| `gray-800` | [#hex] | |
| `gray-900` | [#hex] | |
| **Semantic** | | |
| `red-[50-900]` | [#hex range] | Error |
| `green-[50-900]` | [#hex range] | Success |
| `yellow-[50-900]` | [#hex range] | Warning |
| `blue-[50-900]` | [#hex range] | Info |

### Semantic Color Tokens

| Token | References | Usage |
|-------|-----------|-------|
| **Backgrounds** | | |
| `color-background-default` | `{gray-50}` | Page background |
| `color-background-surface` | [value] | Card and panel backgrounds |
| `color-background-surface-hover` | [value] | Hovered surface |
| `color-background-subtle` | [value] | Section differentiation |
| `color-background-inverse` | [value] | Dark backgrounds |
| **Text** | | |
| `color-text-primary` | `{gray-900}` | Headings, primary content |
| `color-text-secondary` | [value] | Supporting text |
| `color-text-tertiary` | [value] | Least emphasis |
| `color-text-inverse` | [value] | Text on dark backgrounds |
| `color-text-on-action` | [value] | Text on action buttons |
| **Actions** | | |
| `color-action-primary` | [value] | Primary buttons, links |
| `color-action-primary-hover` | [value] | |
| `color-action-primary-active` | [value] | |
| `color-action-secondary` | [value] | Secondary buttons |
| **Borders** | | |
| `color-border-default` | [value] | Standard borders |
| `color-border-strong` | [value] | Emphasized borders |
| `color-border-focus` | [value] | Focus rings |
| **Feedback** | | |
| `color-feedback-error` | [value] | Error text and borders |
| `color-feedback-error-bg` | [value] | Error background |
| `color-feedback-success` | [value] | |
| `color-feedback-success-bg` | [value] | |
| `color-feedback-warning` | [value] | |
| `color-feedback-warning-bg` | [value] | |
| `color-feedback-info` | [value] | |
| `color-feedback-info-bg` | [value] | |

---

## Typography Tokens

### Scale

**Base size:** [16px]
**Scale ratio:** [1.25 — Major Third]

| Token | Value | Line Height |
|-------|-------|-------------|
| `font-size-xs` | [12px] | [1.5] |
| `font-size-sm` | [14px] | [1.5] |
| `font-size-md` | [16px] | [1.5] |
| `font-size-lg` | [20px] | [1.4] |
| `font-size-xl` | [25px] | [1.3] |
| `font-size-2xl` | [31px] | [1.25] |
| `font-size-3xl` | [39px] | [1.2] |
| `font-size-4xl` | [49px] | [1.1] |

### Font Families

| Token | Value | Usage |
|-------|-------|-------|
| `font-family-heading` | [Font stack] | Headings and display text |
| `font-family-body` | [Font stack] | Body text and UI |
| `font-family-mono` | [Font stack] | Code and data |

### Font Weights

| Token | Value |
|-------|-------|
| `font-weight-regular` | 400 |
| `font-weight-medium` | 500 |
| `font-weight-semibold` | 600 |
| `font-weight-bold` | 700 |

### Semantic Typography Tokens

| Token | Size | Weight | Family | Usage |
|-------|------|--------|--------|-------|
| `font-heading-xl` | `{font-size-3xl}` | `{font-weight-bold}` | `{font-family-heading}` | Page title |
| `font-heading-lg` | `{font-size-2xl}` | `{font-weight-semibold}` | `{font-family-heading}` | Section heading |
| `font-heading-md` | `{font-size-xl}` | `{font-weight-semibold}` | `{font-family-heading}` | Sub-section heading |
| `font-heading-sm` | `{font-size-lg}` | `{font-weight-medium}` | `{font-family-heading}` | Card title |
| `font-body-lg` | `{font-size-lg}` | `{font-weight-regular}` | `{font-family-body}` | Lead paragraph |
| `font-body-md` | `{font-size-md}` | `{font-weight-regular}` | `{font-family-body}` | Default body |
| `font-body-sm` | `{font-size-sm}` | `{font-weight-regular}` | `{font-family-body}` | Secondary, labels |
| `font-caption` | `{font-size-xs}` | `{font-weight-regular}` | `{font-family-body}` | Captions, footnotes |

---

## Spacing Tokens

**Base unit:** [8px]

| Token | Value | Usage |
|-------|-------|-------|
| `space-0` | 0px | Reset |
| `space-1` | [4px] | Tight inline (icon-to-label) |
| `space-2` | [8px] | Default inline, small gaps |
| `space-3` | [12px] | Between related elements |
| `space-4` | [16px] | Default padding, form field gaps |
| `space-6` | [24px] | Between components |
| `space-8` | [32px] | Between sections |
| `space-12` | [48px] | Major section breaks |
| `space-16` | [64px] | Page margins, hero padding |

---

## Border Tokens

| Token | Value |
|-------|-------|
| `border-width-sm` | [1px] |
| `border-width-md` | [2px] |
| `border-radius-sm` | [4px] |
| `border-radius-md` | [8px] |
| `border-radius-lg` | [12px] |
| `border-radius-full` | [9999px] |

---

## Shadow Tokens

| Token | Value | Usage |
|-------|-------|-------|
| `shadow-sm` | [0 1px 2px rgba(0,0,0,0.05)] | Cards, subtle elevation |
| `shadow-md` | [0 4px 6px rgba(0,0,0,0.07)] | Dropdowns, hover cards |
| `shadow-lg` | [0 10px 15px rgba(0,0,0,0.1)] | Modals, popovers |
| `shadow-xl` | [0 20px 25px rgba(0,0,0,0.15)] | Dialogs, toasts |

---

## Motion Tokens

| Token | Value | Usage |
|-------|-------|-------|
| `motion-duration-instant` | 0ms | No animation |
| `motion-duration-fast` | [100ms] | Hover, toggle |
| `motion-duration-normal` | [200ms] | Open, appear |
| `motion-duration-slow` | [300ms] | Page transition |
| `motion-easing-standard` | [cubic-bezier(0.2, 0, 0, 1)] | General purpose |
| `motion-easing-enter` | [cubic-bezier(0, 0, 0.2, 1)] | Elements appearing |
| `motion-easing-exit` | [cubic-bezier(0.4, 0, 1, 1)] | Elements leaving |

---

## Theme Overrides

### Light Theme (Default)

[All semantic tokens above define the light theme]

### Dark Theme

| Token | Light Value | Dark Value |
|-------|------------|------------|
| `color-background-default` | [light value] | [dark value] |
| `color-background-surface` | [light value] | [dark value] |
| `color-text-primary` | [light value] | [dark value] |
| `color-text-secondary` | [light value] | [dark value] |
| `color-border-default` | [light value] | [dark value] |
| `shadow-sm` | [light value] | [dark value] |

---

## Delivery

| Platform | Format | Build Tool |
|----------|--------|-----------|
| Web (CSS) | CSS custom properties | [Tool] |
| Web (JS) | ES module | [Tool] |
| iOS | [Format] | [Tool] |
| Android | [Format] | [Tool] |
| Figma | Figma Variables | [Tool] |
