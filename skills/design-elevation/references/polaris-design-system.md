# Shopify Polaris Design System Reference

A comprehensive reference for building interfaces that conform to Shopify's Polaris Design System. Use this when the user requests Polaris styling, Shopify branding, or when building Shopify apps, admin interfaces, or merchant-facing products.

Source: [polaris.shopify.com](https://polaris.shopify.com) and [@shopify/polaris](https://github.com/Shopify/polaris)

---

## Design Philosophy

Polaris is Shopify's design system for building merchant experiences in the Shopify admin and ecosystem. It prioritizes:

- **Merchant focus** - designed for commerce operators managing stores, orders, and products
- **Efficiency** - optimized for task completion in admin workflows
- **Consistency** - unified experience across the entire Shopify admin
- **Accessibility** - WCAG 2.1 AA compliance throughout
- **Adaptability** - light and dark mode, responsive across breakpoints
- **Content-first** - clear, actionable language over decorative UI

The aesthetic is clean, functional, and slightly warm. Think admin dashboard for small-to-medium business owners -- approachable but professional.

---

## Typography

### Font Family
```css
font-family: -apple-system, BlinkMacSystemFont, 'San Francisco', 'Segoe UI',
  Roboto, 'Helvetica Neue', sans-serif;
```

Polaris uses the system font stack -- no custom web font. This ensures fast loading and native feel across platforms.

### Font Size Tokens
| Token | Value | Rem |
|-------|-------|-----|
| `--p-font-size-275` | 11px | 0.6875rem |
| `--p-font-size-300` | 12px | 0.75rem |
| `--p-font-size-325` | 13px | 0.8125rem |
| `--p-font-size-350` | 14px | 0.875rem |
| `--p-font-size-400` | 16px | 1rem |
| `--p-font-size-450` | 18px | 1.125rem |
| `--p-font-size-500` | 20px | 1.25rem |
| `--p-font-size-550` | 22px | 1.375rem |
| `--p-font-size-600` | 24px | 1.5rem |
| `--p-font-size-700` | 28px | 1.75rem |
| `--p-font-size-750` | 30px | 1.875rem |
| `--p-font-size-800` | 32px | 2rem |
| `--p-font-size-900` | 36px | 2.25rem |
| `--p-font-size-1000` | 40px | 2.5rem |

### Font Weight Tokens
| Token | Value | Usage |
|-------|-------|-------|
| `--p-font-weight-regular` | 400 | Body text, descriptions |
| `--p-font-weight-medium` | 500 | Emphasis, subheadings |
| `--p-font-weight-semibold` | 600 | Buttons, labels, badges |
| `--p-font-weight-bold` | 700 | Headings, strong emphasis |

### Line Height Tokens
| Token | Value |
|-------|-------|
| `--p-font-line-height-300` | 16px (1rem) |
| `--p-font-line-height-400` | 20px (1.25rem) |
| `--p-font-line-height-500` | 24px (1.5rem) |
| `--p-font-line-height-600` | 28px (1.75rem) |
| `--p-font-line-height-700` | 32px (2rem) |
| `--p-font-line-height-800` | 36px (2.25rem) |
| `--p-font-line-height-1000` | 44px (2.75rem) |
| `--p-font-line-height-1200` | 52px (3.25rem) |

### Letter Spacing Tokens
| Token | Value |
|-------|-------|
| `--p-font-letter-spacing-densest` | -0.54px |
| `--p-font-letter-spacing-denser` | -0.3px |
| `--p-font-letter-spacing-dense` | -0.2px |
| `--p-font-letter-spacing-normal` | 0 |

### Type Scale (Semantic Variants)
| Variant | Size | Weight | Line Height | Letter Spacing |
|---------|------|--------|-------------|----------------|
| headingXs | 13px | 600 | 20px | normal |
| headingSm | 14px | 600 | 20px | normal |
| headingMd | 14px | 600 | 20px | normal |
| headingLg | 16px | 600 | 24px | normal |
| headingXl | 20px | 600 | 24px | normal |
| heading2xl | 24px | 700 | 28px | dense |
| heading3xl | 28px | 700 | 32px | denser |
| bodyXs | 11px | 400 | 16px | normal |
| bodySm | 12px | 400 | 16px | normal |
| bodyMd | 13px | 400 | 20px | normal |
| bodyLg | 14px | 400 | 20px | normal |

### Key Rules
- Body text defaults to 13px (`bodyMd`), NOT 16px
- System font stack only -- no Google Fonts needed
- Use `font-variant-numeric: tabular-nums` for all data/number displays
- Headings use semibold (600) for smaller sizes, bold (700) for 2xl+

---

## Color System

Polaris uses semantic color tokens that automatically adapt between light and dark modes. All colors are referenced via CSS custom properties.

### Background Colors
| Token | Light Mode | Dark Mode | Usage |
|-------|-----------|-----------|-------|
| `--p-color-bg` | `#FFFFFF` | `#1A1A1A` | Default page background |
| `--p-color-bg-surface` | `#FFFFFF` | `#303030` | Cards, panels, elevated surfaces |
| `--p-color-bg-surface-hover` | `#F7F7F7` | `#3A3A3A` | Surface hover state |
| `--p-color-bg-surface-active` | `#F1F1F1` | `#444444` | Surface pressed state |
| `--p-color-bg-surface-selected` | `#F2F2F2` | `#404040` | Selected surface state |
| `--p-color-bg-surface-secondary` | `#F7F7F7` | `#1A1A1A` | Secondary surfaces |
| `--p-color-bg-surface-tertiary` | `#F3F3F3` | `#2A2A2A` | Tertiary surfaces |
| `--p-color-bg-surface-brand` | `#008060` | `#008060` | Brand-colored surfaces |
| `--p-color-bg-surface-brand-hover` | `#006E52` | `#33997A` | Brand surface hover |
| `--p-color-bg-surface-brand-active` | `#005C43` | `#4DAF8F` | Brand surface active |
| `--p-color-bg-surface-brand-selected` | `#005C43` | `#4DAF8F` | Brand surface selected |
| `--p-color-bg-surface-info` | `#EBF5FA` | `#1A2E3B` | Info banner background |
| `--p-color-bg-surface-success` | `#F1F8F5` | `#1A2E22` | Success banner background |
| `--p-color-bg-surface-warning` | `#FFF8E6` | `#3B2E1A` | Warning banner background |
| `--p-color-bg-surface-critical` | `#FFF4F4` | `#3B1A1A` | Critical/error background |
| `--p-color-bg-fill` | `#303030` | `#E3E3E3` | Solid fill backgrounds |
| `--p-color-bg-fill-hover` | `#3A3A3A` | `#D9D9D9` | Solid fill hover |
| `--p-color-bg-fill-active` | `#444444` | `#CCCCCC` | Solid fill active |
| `--p-color-bg-fill-brand` | `#008060` | `#008060` | Primary brand fill (buttons) |
| `--p-color-bg-fill-brand-hover` | `#006E52` | `#33997A` | Brand fill hover |
| `--p-color-bg-fill-brand-active` | `#005C43` | `#4DAF8F` | Brand fill pressed |
| `--p-color-bg-fill-brand-selected` | `#005C43` | `#4DAF8F` | Brand fill selected |
| `--p-color-bg-fill-brand-disabled` | `#99C4B4` | `#334D43` | Brand fill disabled |
| `--p-color-bg-fill-info` | `#2C6ECB` | `#4B8ADB` | Info fill |
| `--p-color-bg-fill-success` | `#008060` | `#33997A` | Success fill |
| `--p-color-bg-fill-warning` | `#B98900` | `#D4A72C` | Warning fill |
| `--p-color-bg-fill-critical` | `#D72C0D` | `#E05A3E` | Critical/destructive fill |
| `--p-color-bg-fill-disabled` | `#EBEBEB` | `#3A3A3A` | Disabled fill |
| `--p-color-bg-fill-secondary` | `#F7F7F7` | `#303030` | Secondary fill bg |
| `--p-color-bg-fill-secondary-hover` | `#F1F1F1` | `#3A3A3A` | Secondary fill hover |
| `--p-color-bg-fill-secondary-active` | `#EBEBEB` | `#444444` | Secondary fill active |
| `--p-color-bg-fill-tertiary` | `#F3F3F3` | `#2A2A2A` | Tertiary fill bg |
| `--p-color-bg-fill-transparent` | `transparent` | `transparent` | Transparent fill |
| `--p-color-bg-fill-transparent-hover` | `rgba(0,0,0,0.05)` | `rgba(255,255,255,0.08)` | Transparent fill hover |
| `--p-color-bg-fill-transparent-active` | `rgba(0,0,0,0.08)` | `rgba(255,255,255,0.12)` | Transparent fill active |
| `--p-color-bg-fill-transparent-selected` | `rgba(0,0,0,0.06)` | `rgba(255,255,255,0.10)` | Transparent fill selected |

### Text Colors
| Token | Light Mode | Dark Mode | Usage |
|-------|-----------|-----------|-------|
| `--p-color-text` | `#303030` | `#E3E3E3` | Primary text |
| `--p-color-text-secondary` | `#6D7175` | `#A1A1A1` | Secondary/subdued text |
| `--p-color-text-disabled` | `#8C9196` | `#6D6D6D` | Disabled text |
| `--p-color-text-brand` | `#008060` | `#5BBF9A` | Brand-colored text |
| `--p-color-text-brand-hover` | `#006E52` | `#7BCFAF` | Brand text hover |
| `--p-color-text-brand-on-bg-fill` | `#FFFFFF` | `#FFFFFF` | Text on brand fill |
| `--p-color-text-brand-on-bg-fill-hover` | `#FFFFFF` | `#FFFFFF` | Text on brand fill hover |
| `--p-color-text-brand-on-bg-fill-active` | `#FFFFFF` | `#FFFFFF` | Text on brand fill active |
| `--p-color-text-brand-on-bg-fill-disabled` | `#FFFFFF` | `#FFFFFF` | Text on brand fill disabled |
| `--p-color-text-info` | `#2C6ECB` | `#6DA5E8` | Info text |
| `--p-color-text-info-on-bg-fill` | `#FFFFFF` | `#FFFFFF` | Text on info fill |
| `--p-color-text-success` | `#008060` | `#5BBF9A` | Success text |
| `--p-color-text-success-on-bg-fill` | `#FFFFFF` | `#FFFFFF` | Text on success fill |
| `--p-color-text-warning` | `#916A00` | `#D4A72C` | Warning text |
| `--p-color-text-warning-on-bg-fill` | `#FFFFFF` | `#1A1200` | Text on warning fill |
| `--p-color-text-critical` | `#D72C0D` | `#E87A63` | Critical/error text |
| `--p-color-text-critical-on-bg-fill` | `#FFFFFF` | `#FFFFFF` | Text on critical fill |
| `--p-color-text-inverse` | `#FFFFFF` | `#1A1A1A` | Inverse text (on dark/light) |
| `--p-color-text-link` | `#005BD3` | `#6DA5E8` | Links (interactive text) |
| `--p-color-text-link-hover` | `#003D8F` | `#8DBDFF` | Link hover |

### Icon Colors
| Token | Light Mode | Dark Mode | Usage |
|-------|-----------|-----------|-------|
| `--p-color-icon` | `#4A4A4A` | `#B5B5B5` | Default icon color |
| `--p-color-icon-secondary` | `#8C9196` | `#7D7D7D` | Secondary icon color |
| `--p-color-icon-disabled` | `#BABEC3` | `#5C5C5C` | Disabled icon color |
| `--p-color-icon-brand` | `#008060` | `#5BBF9A` | Brand icon color |
| `--p-color-icon-info` | `#2C6ECB` | `#6DA5E8` | Info icon color |
| `--p-color-icon-success` | `#008060` | `#5BBF9A` | Success icon color |
| `--p-color-icon-warning` | `#B98900` | `#D4A72C` | Warning icon color |
| `--p-color-icon-critical` | `#D72C0D` | `#E87A63` | Critical icon color |
| `--p-color-icon-interactive` | `#005BD3` | `#6DA5E8` | Interactive/link icon |

### Border Colors
| Token | Light Mode | Dark Mode | Usage |
|-------|-----------|-----------|-------|
| `--p-color-border` | `#C9CCCF` | `#505050` | Default border |
| `--p-color-border-hover` | `#999EA4` | `#6D6D6D` | Border hover |
| `--p-color-border-disabled` | `#EBEBEB` | `#3A3A3A` | Disabled border |
| `--p-color-border-secondary` | `#E1E3E5` | `#404040` | Subtle/secondary border |
| `--p-color-border-tertiary` | `#F3F3F3` | `#303030` | Very subtle border |
| `--p-color-border-focus` | `#005BD3` | `#6DA5E8` | Focus ring border |
| `--p-color-border-brand` | `#008060` | `#5BBF9A` | Brand border |
| `--p-color-border-info` | `#A4C8E1` | `#2C5282` | Info border |
| `--p-color-border-success` | `#95C9B4` | `#1A5C3A` | Success border |
| `--p-color-border-warning` | `#E1B878` | `#664D00` | Warning border |
| `--p-color-border-critical` | `#E0A5A0` | `#6B1D0D` | Critical border |
| `--p-color-border-critical-secondary` | `#D72C0D` | `#E87A63` | Strong critical border |
| `--p-color-border-interactive` | `#005BD3` | `#6DA5E8` | Interactive element border |
| `--p-color-border-interactive-hover` | `#003D8F` | `#8DBDFF` | Interactive hover border |
| `--p-color-border-interactive-focus` | `#005BD3` | `#6DA5E8` | Interactive focus border |
| `--p-color-border-interactive-active` | `#003D8F` | `#8DBDFF` | Interactive active border |
| `--p-color-border-interactive-disabled` | `#BABEC3` | `#5C5C5C` | Interactive disabled border |

### Brand / Shopify Green
| Name | Hex | Usage |
|------|-----|-------|
| Shopify Green (primary) | `#008060` | Primary brand, primary buttons, success |
| Shopify Green Dark | `#006E52` | Hover states |
| Shopify Green Darker | `#005C43` | Active/pressed states |
| Shopify Green Light | `#5BBF9A` | Dark mode primary text/icons |

### Semantic Color Summary
| Role | Light Mode | Dark Mode |
|------|-----------|-----------|
| Primary/Brand | `#008060` (green) | `#008060` |
| Interactive | `#005BD3` (blue) | `#6DA5E8` |
| Success | `#008060` | `#5BBF9A` |
| Warning | `#B98900` | `#D4A72C` |
| Critical/Destructive | `#D72C0D` | `#E87A63` |
| Info | `#2C6ECB` | `#6DA5E8` |

---

## Spacing

### Spacing Scale
Polaris uses a 4px base unit spacing scale:

| Token | Value |
|-------|-------|
| `--p-space-0` | 0 |
| `--p-space-025` | 1px (0.0625rem) |
| `--p-space-050` | 2px (0.125rem) |
| `--p-space-100` | 4px (0.25rem) |
| `--p-space-150` | 6px (0.375rem) |
| `--p-space-200` | 8px (0.5rem) |
| `--p-space-300` | 12px (0.75rem) |
| `--p-space-400` | 16px (1rem) |
| `--p-space-500` | 20px (1.25rem) |
| `--p-space-600` | 24px (1.5rem) |
| `--p-space-800` | 32px (2rem) |
| `--p-space-1000` | 40px (2.5rem) |
| `--p-space-1200` | 48px (3rem) |
| `--p-space-1600` | 64px (4rem) |
| `--p-space-2000` | 80px (5rem) |
| `--p-space-2400` | 96px (6rem) |
| `--p-space-2800` | 112px (7rem) |
| `--p-space-3200` | 128px (8rem) |

### Key Spacing Rules
- 4px base unit, consistent throughout
- Component internal padding typically uses `--p-space-200` (8px) to `--p-space-400` (16px)
- Card padding: `--p-space-400` (16px) or `--p-space-500` (20px)
- Section spacing: `--p-space-400` to `--p-space-800`
- Page-level padding: `--p-space-400` to `--p-space-600`

---

## Borders & Radius

### Border Radius Tokens
| Token | Value | Usage |
|-------|-------|-------|
| `--p-border-radius-0` | 0 | No rounding |
| `--p-border-radius-050` | 2px (0.125rem) | Small elements, badges |
| `--p-border-radius-100` | 4px (0.25rem) | Inputs, small buttons |
| `--p-border-radius-150` | 6px (0.375rem) | Medium elements |
| `--p-border-radius-200` | 8px (0.5rem) | Cards, popovers, modals |
| `--p-border-radius-300` | 12px (0.75rem) | Large cards, banners |
| `--p-border-radius-400` | 16px (1rem) | Extra-large containers |
| `--p-border-radius-500` | 20px (1.25rem) | Pill shapes |
| `--p-border-radius-750` | 30px (1.875rem) | Full pill |
| `--p-border-radius-full` | 9999px | Circle/pill |

**Important:** Polaris uses larger radii than many enterprise systems. Cards default to `8px` (`--p-border-radius-200`). Buttons use `8px`. This gives the softer, more approachable Shopify feel.

### Border Width Tokens
| Token | Value |
|-------|-------|
| `--p-border-width-0` | 0 |
| `--p-border-width-0165` | 0.66px |
| `--p-border-width-025` | 1px |
| `--p-border-width-050` | 2px |
| `--p-border-width-100` | 4px |

### Common Borders
```css
/* Default card/surface border */
border: var(--p-border-width-025) solid var(--p-color-border);
/* 1px solid #C9CCCF (light) or #505050 (dark) */

/* Input border */
border: var(--p-border-width-025) solid var(--p-color-border);

/* Focus border */
border: var(--p-border-width-050) solid var(--p-color-border-focus);
/* 2px solid #005BD3 */

/* Divider */
border-top: var(--p-border-width-025) solid var(--p-color-border-secondary);
```

---

## Shadows

### Shadow Tokens
| Token | Value | Usage |
|-------|-------|-------|
| `--p-shadow-0` | `none` | No shadow |
| `--p-shadow-100` | `0 1px 0 0 rgba(0,0,0,0.05)` | Minimal elevation, divider shadow |
| `--p-shadow-200` | `0 1px 2px 0 rgba(0,0,0,0.15)` | Cards, low elevation |
| `--p-shadow-300` | `0 2px 4px 0 rgba(26,26,26,0.1), 0 1px 6px 0 rgba(26,26,26,0.05)` | Elevated cards, popovers |
| `--p-shadow-400` | `0 4px 12px 0 rgba(26,26,26,0.12), 0 2px 6px 0 rgba(26,26,26,0.04)` | Dropdowns, action menus |
| `--p-shadow-500` | `0 8px 20px 0 rgba(26,26,26,0.12), 0 3px 8px 0 rgba(26,26,26,0.06)` | Modals, dialogs |
| `--p-shadow-600` | `0 12px 32px -4px rgba(26,26,26,0.16), 0 4px 12px 0 rgba(26,26,26,0.08)` | Maximum elevation, toasts |

### Shadow (Dark Mode)
In dark mode, shadows use stronger opacity values since dark surfaces need more pronounced shadows:

| Token | Dark Mode Value |
|-------|----------------|
| `--p-shadow-200` | `0 1px 2px 0 rgba(0,0,0,0.40)` |
| `--p-shadow-300` | `0 2px 4px 0 rgba(0,0,0,0.30), 0 1px 6px 0 rgba(0,0,0,0.15)` |
| `--p-shadow-400` | `0 4px 12px 0 rgba(0,0,0,0.35), 0 2px 6px 0 rgba(0,0,0,0.15)` |
| `--p-shadow-500` | `0 8px 20px 0 rgba(0,0,0,0.40), 0 3px 8px 0 rgba(0,0,0,0.20)` |
| `--p-shadow-600` | `0 12px 32px -4px rgba(0,0,0,0.50), 0 4px 12px 0 rgba(0,0,0,0.25)` |

### Inset Shadows
| Token | Value | Usage |
|-------|-------|-------|
| `--p-shadow-inset-100` | `inset 0 1px 1px 0 rgba(0,0,0,0.08)` | Pressed state, recessed inputs |
| `--p-shadow-inset-200` | `inset 0 2px 1px 0 rgba(0,0,0,0.15)` | Deeply pressed state |

### Focus Ring
```css
/* Standard focus ring */
box-shadow: 0 0 0 2px var(--p-color-border-focus); /* #005BD3 */
outline: 1px solid transparent;

/* Focus ring on dark backgrounds */
box-shadow: 0 0 0 2px var(--p-color-border-focus); /* #6DA5E8 */
```

**Note:** Polaris uses directional shadows (Y-offset), unlike Modus which uses uniform spread. This gives a natural light-from-above effect.

---

## Z-Index Scale

| Token | Value | Usage |
|-------|-------|-------|
| `--p-z-index-1` | 100 | Sticky headers, fixed elements |
| `--p-z-index-2` | 400 | Popovers, tooltips |
| `--p-z-index-3` | 510 | Navigation overlays |
| `--p-z-index-4` | 512 | Skip-to-content link |
| `--p-z-index-5` | 513 | Toast notifications |
| `--p-z-index-6` | 514 | Backdrop/overlay |
| `--p-z-index-7` | 515 | Modal dialogs |
| `--p-z-index-8` | 516 | Sheet panels |
| `--p-z-index-9` | 517 | Top-level popovers in modals |
| `--p-z-index-10` | 518 | Navigation sidebar |
| `--p-z-index-11` | 519 | Top bar |
| `--p-z-index-12` | 520 | Global loading bar |

---

## Motion / Animation

### Duration Tokens
| Token | Value | Usage |
|-------|-------|-------|
| `--p-motion-duration-0` | 0ms | Instant |
| `--p-motion-duration-50` | 50ms | Micro interactions |
| `--p-motion-duration-100` | 100ms | Quick feedback (hover, active) |
| `--p-motion-duration-150` | 150ms | Color transitions, fades |
| `--p-motion-duration-200` | 200ms | Standard transitions |
| `--p-motion-duration-250` | 250ms | Moderate transitions |
| `--p-motion-duration-300` | 300ms | Popovers, dropdowns |
| `--p-motion-duration-350` | 350ms | Modal entry |
| `--p-motion-duration-400` | 400ms | Page transitions |
| `--p-motion-duration-450` | 450ms | Complex animations |
| `--p-motion-duration-500` | 500ms | Slow transitions |
| `--p-motion-duration-5000` | 5000ms | Loading skeleton |

### Easing Tokens
| Token | Value | Usage |
|-------|-------|-------|
| `--p-motion-ease` | `cubic-bezier(0.25, 0.1, 0.25, 1)` | General purpose ease |
| `--p-motion-ease-in` | `cubic-bezier(0.42, 0, 1, 1)` | Entering elements |
| `--p-motion-ease-out` | `cubic-bezier(0, 0, 0.58, 1)` | Exiting elements |
| `--p-motion-ease-in-out` | `cubic-bezier(0.42, 0, 0.58, 1)` | Symmetric transitions |
| `--p-motion-linear` | `linear` | Progress bars, loading |

### Motion Keyframes
| Token | Usage |
|-------|-------|
| `--p-motion-keyframes-bounce` | Bounce effect for emphasis |
| `--p-motion-keyframes-fade-in` | Fade in entry |
| `--p-motion-keyframes-pulse` | Pulsing skeleton/loading |
| `--p-motion-keyframes-spin` | Spinner rotation |
| `--p-motion-keyframes-appear-above` | Slide up from below |
| `--p-motion-keyframes-appear-below` | Slide down from above |

---

## Component Patterns

### Buttons
```css
/* Primary (filled green) */
background: var(--p-color-bg-fill-brand); /* #008060 */
color: var(--p-color-text-brand-on-bg-fill); /* #FFFFFF */
border-radius: var(--p-border-radius-200); /* 8px */
min-height: 36px;
padding: 6px 16px;
font-size: 13px; /* bodyMd */
font-weight: 600;
line-height: 20px;
border: none;
cursor: pointer;
transition: background var(--p-motion-duration-150) var(--p-motion-ease);

/* Primary hover */
background: var(--p-color-bg-fill-brand-hover); /* #006E52 */

/* Primary active */
background: var(--p-color-bg-fill-brand-active); /* #005C43 */

/* Secondary (default/plain) */
background: var(--p-color-bg-fill-secondary); /* #F7F7F7 */
color: var(--p-color-text); /* #303030 */
border: var(--p-border-width-0165) solid var(--p-color-border); /* 0.66px solid #C9CCCF */
border-radius: var(--p-border-radius-200); /* 8px */

/* Secondary hover */
background: var(--p-color-bg-fill-secondary-hover); /* #F1F1F1 */

/* Tertiary / Plain */
background: transparent;
color: var(--p-color-text-link); /* #005BD3 */
text-decoration: underline;
border: none;
padding: 2px 6px;

/* Destructive / Critical */
background: var(--p-color-bg-fill-critical); /* #D72C0D */
color: var(--p-color-text-critical-on-bg-fill); /* #FFFFFF */

/* Disabled (all variants) */
background: var(--p-color-bg-fill-disabled); /* #EBEBEB */
color: var(--p-color-text-disabled); /* #8C9196 */
pointer-events: none;

/* Focus ring (all variants) */
box-shadow: 0 0 0 2px #005BD3;
outline: 1px solid transparent;

/* Button sizes */
/* Micro: min-height 20px, padding 0 6px, font-size 12px */
/* Slim: min-height 28px, padding 2px 8px, font-size 12px */
/* Medium (default): min-height 36px, padding 6px 16px, font-size 13px */
/* Large: min-height 44px, padding 10px 24px, font-size 15px */

/* Full width */
width: 100%;
display: block;
```

### Cards (LegacyCard / Card)
```css
/* Card */
background: var(--p-color-bg-surface); /* #FFFFFF */
border-radius: var(--p-border-radius-300); /* 12px */
box-shadow: var(--p-shadow-200); /* 0 1px 2px 0 rgba(0,0,0,0.15) */
overflow: hidden;

/* Card with border (no shadow variant) */
background: var(--p-color-bg-surface);
border: var(--p-border-width-025) solid var(--p-color-border-secondary);
border-radius: var(--p-border-radius-300); /* 12px */

/* Card header */
padding: var(--p-space-400); /* 16px */
display: flex;
align-items: center;
justify-content: space-between;

/* Card section */
padding: var(--p-space-400); /* 16px */
border-top: var(--p-border-width-025) solid var(--p-color-border-secondary);

/* Card footer */
padding: var(--p-space-400);
border-top: var(--p-border-width-025) solid var(--p-color-border-secondary);

/* Subdued card section */
background: var(--p-color-bg-surface-secondary); /* #F7F7F7 */
```

### Data Tables
```css
/* Table container */
background: var(--p-color-bg-surface);
border-radius: var(--p-border-radius-300); /* 12px */
overflow: hidden;

/* Table header */
background: var(--p-color-bg-surface-secondary); /* #F7F7F7 */
border-bottom: var(--p-border-width-025) solid var(--p-color-border-secondary);

/* Header cell */
padding: var(--p-space-200) var(--p-space-400); /* 8px 16px */
font-size: 12px;
font-weight: 600;
color: var(--p-color-text-secondary); /* #6D7175 */
text-align: left;

/* Table row */
border-bottom: var(--p-border-width-025) solid var(--p-color-border-secondary);

/* Table cell */
padding: var(--p-space-300) var(--p-space-400); /* 12px 16px */
font-size: 13px;
color: var(--p-color-text);
vertical-align: middle;

/* Row hover */
background: var(--p-color-bg-surface-hover); /* #F7F7F7 */

/* Row selected */
background: var(--p-color-bg-surface-selected); /* #F2F2F2 */

/* Sortable header */
cursor: pointer;
/* Sort icon appears on hover */

/* Numeric column alignment */
text-align: right;
font-variant-numeric: tabular-nums;

/* Totals row */
font-weight: 600;
background: var(--p-color-bg-surface-secondary);
```

### Navigation / Nav
```css
/* Sidebar navigation */
width: 240px;
background: var(--p-color-bg-surface);
border-right: var(--p-border-width-025) solid var(--p-color-border-secondary);
padding: var(--p-space-200) 0;

/* Nav item */
display: flex;
align-items: center;
gap: var(--p-space-200); /* 8px */
padding: var(--p-space-100) var(--p-space-300); /* 4px 12px */
min-height: 32px;
font-size: 13px;
font-weight: 400;
color: var(--p-color-text);
border-radius: var(--p-border-radius-200); /* 8px */
margin: 0 var(--p-space-200); /* 0 8px */
text-decoration: none;
cursor: pointer;

/* Nav item hover */
background: var(--p-color-bg-surface-hover); /* #F7F7F7 */
color: var(--p-color-text);

/* Nav item active/selected */
background: var(--p-color-bg-surface-selected); /* #F2F2F2 */
font-weight: 600;
color: var(--p-color-text);

/* Nav item with icon */
/* Icon: 20px, color: var(--p-color-icon) */

/* Nav section title */
font-size: 12px;
font-weight: 600;
color: var(--p-color-text-secondary);
text-transform: uppercase;
letter-spacing: 0.05em;
padding: var(--p-space-300) var(--p-space-300) var(--p-space-100);

/* Nav sub-item */
padding-left: var(--p-space-800); /* 32px indent */
```

### Top Bar
```css
/* Top bar / Frame header */
height: 56px;
background: #1A1A1A; /* Shopify admin uses dark top bar */
color: #FFFFFF;
display: flex;
align-items: center;
padding: 0 var(--p-space-400);
z-index: var(--p-z-index-11); /* 519 */

/* Search bar within top bar */
background: rgba(255, 255, 255, 0.12);
border-radius: var(--p-border-radius-200); /* 8px */
height: 36px;
color: #FFFFFF;
flex: 1;
max-width: 580px;

/* Top bar icons */
color: rgba(255, 255, 255, 0.8);
/* Hover: color: #FFFFFF */
```

### Inputs / Text Fields
```css
/* Default input */
background: var(--p-color-bg-surface); /* #FFFFFF */
color: var(--p-color-text); /* #303030 */
border: var(--p-border-width-0165) solid var(--p-color-border); /* 0.66px solid #C9CCCF */
border-radius: var(--p-border-radius-200); /* 8px */
padding: var(--p-space-150) var(--p-space-300); /* 6px 12px */
min-height: 36px;
font-size: 13px;
line-height: 20px;

/* Input hover */
border-color: var(--p-color-border-hover); /* #999EA4 */

/* Input focus */
border-color: var(--p-color-border-focus); /* #005BD3 */
box-shadow: 0 0 0 1px var(--p-color-border-focus);
outline: none;

/* Input error / critical */
border-color: var(--p-color-border-critical-secondary); /* #D72C0D */
box-shadow: 0 0 0 1px var(--p-color-border-critical-secondary);

/* Placeholder */
color: var(--p-color-text-secondary); /* #6D7175 */

/* Label */
font-size: 13px;
font-weight: 400;
color: var(--p-color-text);
margin-bottom: var(--p-space-100); /* 4px */

/* Help text */
font-size: 12px;
color: var(--p-color-text-secondary);
margin-top: var(--p-space-100);

/* Disabled */
background: var(--p-color-bg-surface-tertiary); /* #F3F3F3 */
color: var(--p-color-text-disabled);
border-color: var(--p-color-border-disabled);
cursor: not-allowed;
```

### Banners
```css
/* Default / Info banner */
background: var(--p-color-bg-surface-info); /* #EBF5FA */
border-radius: var(--p-border-radius-300); /* 12px */
padding: var(--p-space-300) var(--p-space-400); /* 12px 16px */
border-left: 4px solid var(--p-color-border-info);

/* Success banner */
background: var(--p-color-bg-surface-success); /* #F1F8F5 */
border-left: 4px solid var(--p-color-border-success);

/* Warning banner */
background: var(--p-color-bg-surface-warning); /* #FFF8E6 */
border-left: 4px solid var(--p-color-border-warning);

/* Critical banner */
background: var(--p-color-bg-surface-critical); /* #FFF4F4 */
border-left: 4px solid var(--p-color-border-critical);

/* Banner title */
font-size: 13px;
font-weight: 600;
color: var(--p-color-text);

/* Banner body */
font-size: 13px;
font-weight: 400;
color: var(--p-color-text);
```

### Badges
```css
/* Default badge */
background: var(--p-color-bg-fill-secondary); /* #F7F7F7 */
color: var(--p-color-text); /* #303030 */
border-radius: var(--p-border-radius-full); /* 9999px - pill */
padding: 2px 8px;
font-size: 12px;
font-weight: 400;
line-height: 16px;
display: inline-flex;
align-items: center;

/* Info badge */
background: #E3F0FF;
color: #1F5199;

/* Success badge */
background: #AEE9D1;
color: #0D5334;

/* Warning badge */
background: #FFD79D;
color: #5E4200;

/* Critical badge */
background: #FED3D1;
color: #6E1612;

/* Attention badge */
background: #FFD79D;
color: #5E4200;

/* New badge */
background: var(--p-color-bg-fill-brand); /* #008060 */
color: #FFFFFF;
```

### Modals
```css
/* Backdrop */
background: rgba(0, 0, 0, 0.5);
position: fixed;
inset: 0;
z-index: var(--p-z-index-6); /* 514 */

/* Modal container */
background: var(--p-color-bg-surface);
border-radius: var(--p-border-radius-300); /* 12px */
box-shadow: var(--p-shadow-600);
max-width: 620px;
width: calc(100% - 32px);
max-height: calc(100vh - 64px);
z-index: var(--p-z-index-7); /* 515 */
overflow: hidden;

/* Modal header */
padding: var(--p-space-400) var(--p-space-500); /* 16px 20px */
border-bottom: var(--p-border-width-025) solid var(--p-color-border-secondary);
display: flex;
align-items: center;
justify-content: space-between;

/* Modal title */
font-size: 16px;
font-weight: 600;
line-height: 24px;

/* Modal body */
padding: var(--p-space-500); /* 20px */
overflow-y: auto;

/* Modal footer */
padding: var(--p-space-400) var(--p-space-500); /* 16px 20px */
border-top: var(--p-border-width-025) solid var(--p-color-border-secondary);
display: flex;
justify-content: flex-end;
gap: var(--p-space-200); /* 8px */
```

### Toast / Snackbar
```css
background: var(--p-color-bg-fill); /* #303030 */
color: var(--p-color-text-inverse); /* #FFFFFF */
border-radius: var(--p-border-radius-200); /* 8px */
padding: var(--p-space-300) var(--p-space-400); /* 12px 16px */
box-shadow: var(--p-shadow-600);
font-size: 13px;
min-height: 44px;
display: flex;
align-items: center;
z-index: var(--p-z-index-5); /* 513 */
```

### Popover
```css
background: var(--p-color-bg-surface);
border-radius: var(--p-border-radius-300); /* 12px */
box-shadow: var(--p-shadow-400);
border: var(--p-border-width-025) solid var(--p-color-border-secondary);
z-index: var(--p-z-index-2); /* 400 */
min-width: 200px;
max-width: 400px;
overflow: hidden;
```

### Tabs
```css
/* Tab container */
display: flex;
border-bottom: var(--p-border-width-025) solid var(--p-color-border-secondary);

/* Tab item */
padding: var(--p-space-200) var(--p-space-400); /* 8px 16px */
font-size: 13px;
font-weight: 400;
color: var(--p-color-text-secondary);
border: none;
background: transparent;
cursor: pointer;
position: relative;
white-space: nowrap;

/* Tab hover */
color: var(--p-color-text);
background: var(--p-color-bg-surface-hover);

/* Tab active/selected */
color: var(--p-color-text);
font-weight: 400;
/* Green bottom border indicator */
border-bottom: 3px solid var(--p-color-border-brand); /* #008060 */
margin-bottom: -1px;

/* Fitted tabs (full width) */
flex: 1;
text-align: center;
```

### Checkbox & Radio
```css
/* Checkbox */
width: 18px;
height: 18px;
border: var(--p-border-width-050) solid var(--p-color-border); /* 2px */
border-radius: var(--p-border-radius-100); /* 4px */
background: var(--p-color-bg-surface);

/* Checkbox checked */
background: var(--p-color-bg-fill-brand); /* #008060 */
border-color: var(--p-color-bg-fill-brand);

/* Radio */
width: 18px;
height: 18px;
border: var(--p-border-width-050) solid var(--p-color-border);
border-radius: var(--p-border-radius-full); /* circle */

/* Radio selected */
border-color: var(--p-color-bg-fill-brand);
/* Inner dot: 8px, #008060 */
```

### Select
```css
/* Select input */
appearance: none;
background: var(--p-color-bg-surface);
border: var(--p-border-width-0165) solid var(--p-color-border);
border-radius: var(--p-border-radius-200); /* 8px */
padding: var(--p-space-150) var(--p-space-800) var(--p-space-150) var(--p-space-300);
min-height: 36px;
font-size: 13px;
color: var(--p-color-text);
/* Chevron icon positioned right */
```

### Loading / Skeleton
```css
/* Skeleton body text */
height: 8px;
background: var(--p-color-bg-fill-tertiary); /* #F3F3F3 */
border-radius: var(--p-border-radius-100); /* 4px */
animation: pulse 1.5s ease-in-out infinite;

/* Skeleton display text */
height: 28px;

/* Skeleton thumbnail */
width: 40px;
height: 40px;
border-radius: var(--p-border-radius-100);

@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.4; }
}
```

### Spinner
```css
width: 20px; /* small */
width: 44px; /* large */
color: var(--p-color-bg-fill-brand); /* #008060 */
animation: spin 500ms linear infinite;
```

### Pagination
```css
/* Pagination button */
min-width: 36px;
min-height: 36px;
border-radius: var(--p-border-radius-200); /* 8px */
border: var(--p-border-width-0165) solid var(--p-color-border);
background: var(--p-color-bg-surface);
display: inline-flex;
align-items: center;
justify-content: center;
```

---

## Dark Mode

### Implementation
```html
<!-- Apply dark mode via class on html or body -->
<html class="p-color-scheme--dark">

<!-- Or via CSS custom property -->
<html style="color-scheme: dark;">
```

### Key Token Swaps
| Property | Light | Dark |
|----------|-------|------|
| Page bg | `#FFFFFF` | `#1A1A1A` |
| Surface bg | `#FFFFFF` | `#303030` |
| Primary text | `#303030` | `#E3E3E3` |
| Secondary text | `#6D7175` | `#A1A1A1` |
| Disabled text | `#8C9196` | `#6D6D6D` |
| Primary/brand | `#008060` | `#008060` |
| Brand text/icon | `#008060` | `#5BBF9A` |
| Interactive/link | `#005BD3` | `#6DA5E8` |
| Critical | `#D72C0D` | `#E87A63` |
| Warning | `#B98900` | `#D4A72C` |
| Border default | `#C9CCCF` | `#505050` |
| Border secondary | `#E1E3E5` | `#404040` |
| Surface hover | `#F7F7F7` | `#3A3A3A` |
| Surface selected | `#F2F2F2` | `#404040` |
| Fill (buttons) | `#303030` | `#E3E3E3` |
| Shadow base | `rgba(0,0,0,0.05-0.16)` | `rgba(0,0,0,0.25-0.50)` |
| Input bg | `#FFFFFF` | `#303030` |
| Top bar | `#1A1A1A` | `#1A1A1A` |

---

## Data Visualization Colors

### Categorical Palette
Use these in order for multi-series charts:
```
#2C6ECB  -- Blue (primary data)
#008060  -- Green
#B98900  -- Yellow
#D72C0D  -- Red
#9C6ADE  -- Purple
#00A0AC  -- Teal
#E06A16  -- Orange
#B44E8B  -- Pink
#8C9196  -- Gray
#3E4345  -- Dark Gray
```

### Sequential / Gradient Palettes
- Blue: `#EBF5FA` -> `#A4C8E1` -> `#2C6ECB` -> `#1F5199` -> `#002E5D`
- Green: `#F1F8F5` -> `#95C9B4` -> `#008060` -> `#005C43` -> `#002E22`

### Semantic Data Colors
- Positive/up: `#008060` (light) / `#5BBF9A` (dark)
- Negative/down: `#D72C0D` (light) / `#E87A63` (dark)
- Warning/caution: `#B98900` (light) / `#D4A72C` (dark)
- Neutral/reference: `#8C9196`

### Chart Styling Rules
- Chart background: transparent
- Gridlines: `var(--p-color-border-secondary)`, horizontal only
- Axis labels: 12px, `var(--p-color-text-secondary)`, system font stack
- Data labels: 12px, semibold, `var(--p-color-text)`
- Titles: 13px, semibold, `var(--p-color-text)`
- Use `tabular-nums` on all number labels
- Border radius on bars: 4px top corners only

---

## Layout Patterns

### App Frame (Standard Shopify Admin Layout)
```
+----------------------------------------------+
| Top Bar (56px, dark #1A1A1A, full width)     |
+----------+-----------------------------------+
| Side Nav | Content area                      |
| (240px)  | (scrollable, padded)              |
|          |                                   |
|          |                                   |
|          |                                   |
+----------+-----------------------------------+
```

### App Shell Dimensions
| Element | Value |
|---------|-------|
| Top bar height | `56px` |
| Navigation width | `240px` |
| Navigation collapsed | `0px` (hidden on mobile) |
| Page max-width | `998px` (narrow), `1200px` (default), `100%` (full-width) |
| Page padding | `var(--p-space-400)` to `var(--p-space-600)` |
| Content vertical spacing | `var(--p-space-400)` |

### Breakpoints
| Name | Value | Usage |
|------|-------|-------|
| xs | `0px` | Mobile portrait |
| sm | `490px` | Mobile landscape |
| md | `768px` | Tablet |
| lg | `1040px` | Desktop (nav appears) |
| xl | `1440px` | Large desktop |

### Page Layout
```css
/* Standard page */
max-width: 998px;
margin: 0 auto;
padding: var(--p-space-400); /* 16px mobile */
padding: var(--p-space-600); /* 24px desktop */

/* Full-width page */
max-width: 100%;

/* Narrow page */
max-width: 752px;

/* Page header */
margin-bottom: var(--p-space-400);

/* Page title */
font-size: 20px;
font-weight: 600;
line-height: 24px;
```

### Content Spacing
- Stack items vertically with `var(--p-space-400)` (16px) gap
- Card grid: use CSS grid with `var(--p-space-400)` gap
- Section spacing: `var(--p-space-600)` to `var(--p-space-800)`
- Inline element gap: `var(--p-space-200)` (8px)

---

## Interaction States

All interactive elements follow this state pattern:

| State | Behavior |
|-------|----------|
| Default | Base styling |
| Hover | Background shift to `--p-color-bg-surface-hover` or `--p-color-bg-fill-*-hover` |
| Active/Pressed | Darker variant `--p-color-bg-surface-active` or `--p-color-bg-fill-*-active` |
| Focus | `box-shadow: 0 0 0 2px var(--p-color-border-focus)` (#005BD3) |
| Disabled | Muted colors, `cursor: not-allowed`, reduced contrast |
| Selected | `--p-color-bg-surface-selected`, may include check icon |

### Transition Defaults
```css
transition-property: background-color, border-color, box-shadow, color;
transition-duration: var(--p-motion-duration-150); /* 150ms */
transition-timing-function: var(--p-motion-ease);
```

---

## Quick Implementation Checklist

When building in Polaris style:

- [ ] Font: System font stack (no Google Fonts needed)
- [ ] Body text: 13px (bodyMd), NOT 14px or 16px
- [ ] Primary brand: `#008060` (Shopify green)
- [ ] Interactive/links: `#005BD3` (blue)
- [ ] Border radius: `8px` on buttons/inputs, `12px` on cards
- [ ] Shadows: directional (Y-offset), not uniform
- [ ] Grays: warm neutral tones, not cool/blue
- [ ] Buttons: 36px min-height, 600 weight, 8px radius
- [ ] Top bar: 56px height, dark (#1A1A1A)
- [ ] Tables: subtle header bg (#F7F7F7), thin borders
- [ ] Disabled: muted colors + `cursor: not-allowed`
- [ ] Focus rings: `0 0 0 2px #005BD3` box-shadow
- [ ] Transitions: `150ms` ease
- [ ] Inputs: 8px radius, 36px min-height, 0.66px border
- [ ] Labels: 13px, regular weight, above input
- [ ] Banners: 12px radius, 4px left border, tinted backgrounds
- [ ] `tabular-nums` on all numbers
- [ ] Cards: 12px radius, subtle shadow or border

---

## Polaris vs. Tailwind Mapping

For teams familiar with Tailwind, here's how Polaris tokens map:

| Polaris | Nearest Tailwind | Note |
|---------|-----------------|------|
| Surface #FFFFFF | `bg-white` | Same in light mode |
| Surface secondary #F7F7F7 | `bg-gray-50` | Very close |
| Border #C9CCCF | `border-gray-300` | Similar neutral gray |
| Text #303030 | `text-gray-800` | Slightly lighter than gray-900 |
| Text secondary #6D7175 | `text-gray-500` | Close match |
| Brand #008060 | `emerald-700` | Shopify green ~ emerald |
| Interactive #005BD3 | `blue-700` | Polaris blue is similar |
| Critical #D72C0D | `red-600` | Close match |
| Warning #B98900 | `amber-600` | Close match |
| Radius 8px | `rounded-lg` | Polaris default = Tailwind rounded-lg |
| Radius 12px (cards) | `rounded-xl` | |
| Shadow-200 | `shadow-sm` | Similar light shadow |
| Shadow-400 | `shadow-md` | |
| Shadow-600 | `shadow-xl` | |
| Body 13px | between `text-xs` and `text-sm` | No exact Tailwind match |
| Space-400 (16px) | `p-4` / `gap-4` | Direct match |

**Critical differences from Tailwind defaults:**
1. Body text is 13px (no Tailwind equivalent -- use custom size or `text-[13px]`)
2. Border radius is `8px` for most controls, `12px` for cards (Tailwind's `rounded` is 4px)
3. Shadows are softer and use rgba(0,0,0,...) not rgba(0,0,0,...)
4. Grays are warm/neutral, not cool (unlike Tailwind's default gray/slate)
5. Primary color is green (#008060), not blue
6. Links/interactive color is blue (#005BD3), separate from brand green
7. Borders are very thin (0.66px), thinner than Tailwind's default 1px

---

## Icon System

Polaris uses its own icon set: `@shopify/polaris-icons`

### Icon Sizes
| Size | Dimensions | Usage |
|------|-----------|-------|
| Small | 16px | Inline with text, badges |
| Medium | 20px | Default, nav items, buttons |
| Large | 24px | Standalone, empty states |

### Icon Colors
- Default: `var(--p-color-icon)` (#4A4A4A)
- Secondary: `var(--p-color-icon-secondary)` (#8C9196)
- Interactive: `var(--p-color-icon-interactive)` (#005BD3)
- Brand: `var(--p-color-icon-brand)` (#008060)
- Critical: `var(--p-color-icon-critical)` (#D72C0D)
- Warning: `var(--p-color-icon-warning)` (#B98900)
- Success: `var(--p-color-icon-success)` (#008060)

---

## Resource List / Index Table

```css
/* Resource list item */
padding: var(--p-space-300) var(--p-space-400); /* 12px 16px */
border-bottom: var(--p-border-width-025) solid var(--p-color-border-secondary);
display: flex;
align-items: center;
gap: var(--p-space-300); /* 12px */
cursor: pointer;

/* Hover */
background: var(--p-color-bg-surface-hover);

/* Selected */
background: var(--p-color-bg-surface-selected);

/* Index table header (sticky) */
position: sticky;
top: 0;
z-index: var(--p-z-index-1);
background: var(--p-color-bg-surface-secondary);
padding: var(--p-space-200) var(--p-space-400);
font-size: 12px;
font-weight: 600;
```

---

## Thumbnail / Avatar

```css
/* Small */
width: 24px; height: 24px;
border-radius: var(--p-border-radius-100); /* 4px */

/* Medium */
width: 40px; height: 40px;
border-radius: var(--p-border-radius-100);

/* Large */
width: 60px; height: 60px;
border-radius: var(--p-border-radius-100);

/* Extra large */
width: 80px; height: 80px;
border-radius: var(--p-border-radius-150);

/* Avatar (circular) */
border-radius: var(--p-border-radius-full); /* 9999px */

/* Initials fallback */
background: var(--p-color-bg-fill-secondary);
color: var(--p-color-text-secondary);
font-weight: 600;
font-size: 12px; /* small */ / 14px; /* medium */
display: flex;
align-items: center;
justify-content: center;
```
