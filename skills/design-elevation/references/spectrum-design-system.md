# Adobe Spectrum Design System Reference

A comprehensive reference for building interfaces that conform to Adobe's Spectrum Design System. Use this when the user requests Spectrum styling, Adobe branding, or when working on Adobe-ecosystem products.

Source: [spectrum.adobe.com](https://spectrum.adobe.com) and [@adobe/spectrum-tokens](https://github.com/adobe/spectrum-tokens), [@spectrum-css](https://github.com/adobe/spectrum-css)

---

## Design Philosophy

Spectrum is Adobe's design system — built for creative, enterprise, and productivity tools across desktop, web, and mobile. It prioritizes:

- **Clarity** — clean, content-first interfaces that stay out of the way
- **Productivity** — optimized for power users with complex, tool-heavy workflows
- **Inclusivity** — WCAG 2.1 AA minimum, AAA where possible
- **Consistency** — shared language across 50+ Adobe products (Creative Cloud, Experience Cloud, Document Cloud)
- **Theming** — four built-in color themes: lightest, light, dark, darkest
- **Scale** — two density modes: medium (desktop) and large (touch/mobile)

The aesthetic is refined, professional, and understated. Spectrum avoids decoration in favor of letting content and creative work take center stage. Think professional creative tools — not consumer marketing.

---

## Typography

### Font Family
```css
/* Spectrum uses Adobe Clean */
font-family: 'Adobe Clean', 'Segoe UI', -apple-system, BlinkMacSystemFont,
  'Helvetica Neue', Arial, sans-serif;

/* For CJK languages */
font-family: 'Adobe Clean Han', 'Segoe UI', sans-serif;

/* Monospace / code */
font-family: 'Source Code Pro', 'Monaco', 'Consolas', 'Courier New', monospace;
```

**Note:** Adobe Clean is a proprietary font. For non-Adobe projects, use the fallback stack or substitute with a similar humanist sans-serif like `Source Sans Pro` (open source, also by Adobe):
```html
<link href="https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@300;400;600;700&display=swap" rel="stylesheet">
```

### Type Scale (Desktop / Medium)
| Role | Size | Rem | Line Height | Weight |
|------|------|-----|-------------|--------|
| Heading XXL | 45px | 2.8125rem | 1.3 (58px) | 700 |
| Heading XL | 36px | 2.25rem | 1.3 (47px) | 700 |
| Heading L | 28px | 1.75rem | 1.3 (36px) | 700 |
| Heading M | 22px | 1.375rem | 1.3 (29px) | 700 |
| Heading S | 18px | 1.125rem | 1.3 (23px) | 700 |
| Heading XS | 16px | 1rem | 1.3 (21px) | 700 |
| Heading XXS | 14px | 0.875rem | 1.3 (18px) | 700 |
| Body XL | 20px | 1.25rem | 1.5 (30px) | 400 |
| Body L | 18px | 1.125rem | 1.5 (27px) | 400 |
| Body M | 16px | 1rem | 1.5 (24px) | 400 |
| Body S | 14px | 0.875rem | 1.5 (21px) | 400 |
| Body XS | 12px | 0.75rem | 1.5 (18px) | 400 |
| Detail / Label S | 11px | 0.6875rem | 1.5 (17px) | 400 |

### Font Weights
- Light: `300` (display text, large headings)
- Regular: `400` (body text, default)
- Semi-bold / Bold: `600` (emphasis, labels)
- Black / Heavy: `700` (headings, strong emphasis)
- Extra Black: `900` (brand/marketing only)

### Key Rules
- Default body text is **14px** for dense UIs, **16px** for reading-heavy UIs
- Headings use `font-weight: 700` with `line-height: 1.3`
- Body text uses `font-weight: 400` with `line-height: 1.5`
- Use `font-variant-numeric: tabular-nums` for data displays
- Detail/label text uses ALL CAPS with `letter-spacing: 0.06em` (0.72px at 12px)
- Minimum readable size: 11px (detail only), prefer 12px+

---

## Color System

### Color Architecture
Spectrum uses a semantic token system with three layers:
1. **Global tokens** — raw palette values (e.g., `blue-800`)
2. **Alias tokens** — semantic meanings (e.g., `accent-color-default`)
3. **Component tokens** — specific component values (e.g., `button-background-color`)

Colors adapt across four themes: **lightest**, **light**, **dark**, **darkest**.

### Gray Scale
| Token | Lightest | Light | Dark | Darkest |
|-------|----------|-------|------|---------|
| gray-50 | `#FFFFFF` | `#FFFFFF` | `#252525` | `#1A1A1A` |
| gray-75 | `#FAFAFA` | `#FAFAFA` | `#2C2C2C` | `#1E1E1E` |
| gray-100 | `#F5F5F5` | `#F5F5F5` | `#323232` | `#222222` |
| gray-200 | `#EAEAEA` | `#E6E6E6` | `#3E3E3E` | `#2C2C2C` |
| gray-300 | `#E1E1E1` | `#D5D5D5` | `#4A4A4A` | `#393939` |
| gray-400 | `#CACACA` | `#B8B8B8` | `#5C5C5C` | `#494949` |
| gray-500 | `#B3B3B3` | `#9D9D9D` | `#6E6E6E` | `#5C5C5C` |
| gray-600 | `#8E8E8E` | `#747474` | `#909090` | `#7C7C7C` |
| gray-700 | `#6E6E6E` | `#505050` | `#B3B3B3` | `#A2A2A2` |
| gray-800 | `#4B4B4B` | `#343434` | `#D5D5D5` | `#CACACA` |
| gray-900 | `#2C2C2C` | `#1A1A1A` | `#EFEFEF` | `#EFEFEF` |

### Blue (Accent) Scale
| Token | Value (Light) |
|-------|---------------|
| blue-100 | `#E0F0FF` |
| blue-200 | `#AADBFF` |
| blue-300 | `#6FC1FF` |
| blue-400 | `#2A9AF4` |
| blue-500 | `#0D80D8` |
| blue-600 | `#0265BB` |
| blue-700 | `#034D92` |
| blue-800 | `#003571` |
| blue-900 | `#002451` |
| blue-1000 | `#001633` |
| blue-1100 | `#000C1F` |
| blue-1200 | `#000510` |
| blue-1300 | `#000208` |

### Red (Negative / Danger) Scale
| Token | Value (Light) |
|-------|---------------|
| red-100 | `#FFE5E5` |
| red-200 | `#FFBDBD` |
| red-300 | `#FF8F8F` |
| red-400 | `#FF5C5C` |
| red-500 | `#EE2323` |
| red-600 | `#D31010` |
| red-700 | `#B40000` |
| red-800 | `#8F0000` |
| red-900 | `#6D0000` |
| red-1000 | `#520000` |

### Orange (Warning) Scale
| Token | Value (Light) |
|-------|---------------|
| orange-100 | `#FFECCC` |
| orange-200 | `#FFD599` |
| orange-300 | `#FFBD66` |
| orange-400 | `#FFA033` |
| orange-500 | `#F28000` |
| orange-600 | `#D66D00` |
| orange-700 | `#AD5600` |
| orange-800 | `#884300` |
| orange-900 | `#6B3400` |
| orange-1000 | `#4F2500` |

### Green (Positive / Success) Scale
| Token | Value (Light) |
|-------|---------------|
| green-100 | `#CEF5CE` |
| green-200 | `#93E793` |
| green-300 | `#51D351` |
| green-400 | `#12B812` |
| green-500 | `#009E00` |
| green-600 | `#008400` |
| green-700 | `#006600` |
| green-800 | `#005200` |
| green-900 | `#003F00` |
| green-1000 | `#002E00` |

### Indigo Scale
| Token | Value (Light) |
|-------|---------------|
| indigo-100 | `#EDEEFF` |
| indigo-200 | `#D3D5FF` |
| indigo-300 | `#B5B8FF` |
| indigo-400 | `#9498FF` |
| indigo-500 | `#7478F0` |
| indigo-600 | `#595CE0` |
| indigo-700 | `#4046CA` |
| indigo-800 | `#2D32A8` |
| indigo-900 | `#1E2382` |
| indigo-1000 | `#131660` |

### Celery (Alt Green) Scale
| Token | Value (Light) |
|-------|---------------|
| celery-400 | `#44B556` |
| celery-500 | `#3DA74E` |
| celery-600 | `#328A3E` |
| celery-700 | `#266E2F` |

### Chartreuse Scale
| Token | Value (Light) |
|-------|---------------|
| chartreuse-400 | `#85D044` |
| chartreuse-500 | `#73B82F` |
| chartreuse-600 | `#5EA118` |

### Cyan Scale
| Token | Value (Light) |
|-------|---------------|
| cyan-400 | `#23B2D4` |
| cyan-500 | `#0FA4C6` |
| cyan-600 | `#0091B2` |
| cyan-700 | `#00788F` |

### Fuchsia Scale
| Token | Value (Light) |
|-------|---------------|
| fuchsia-400 | `#CF3EDF` |
| fuchsia-500 | `#BC25CC` |
| fuchsia-600 | `#A211B5` |
| fuchsia-700 | `#880F9A` |

### Magenta Scale
| Token | Value (Light) |
|-------|---------------|
| magenta-400 | `#E6318B` |
| magenta-500 | `#D4167B` |
| magenta-600 | `#B80966` |
| magenta-700 | `#970452` |

### Purple Scale
| Token | Value (Light) |
|-------|---------------|
| purple-400 | `#A96EE8` |
| purple-500 | `#9656D6` |
| purple-600 | `#7E41C1` |
| purple-700 | `#6730A6` |
| purple-800 | `#512089` |

### Seafoam Scale
| Token | Value (Light) |
|-------|---------------|
| seafoam-400 | `#20A3A8` |
| seafoam-500 | `#0E9297` |
| seafoam-600 | `#007F83` |
| seafoam-700 | `#006B6E` |

### Yellow Scale
| Token | Value (Light) |
|-------|---------------|
| yellow-100 | `#FFF3C4` |
| yellow-200 | `#FFE78A` |
| yellow-300 | `#FFD950` |
| yellow-400 | `#EDCA00` |
| yellow-500 | `#D9B500` |
| yellow-600 | `#BF9C00` |
| yellow-700 | `#9D7E00` |
| yellow-800 | `#7C6300` |
| yellow-900 | `#604D00` |
| yellow-1000 | `#473700` |

### Semantic Color Roles
| Role | Light Theme Token | Light Value | Dark Value |
|------|-------------------|-------------|------------|
| Background (page) | `gray-50` | `#FFFFFF` | `#252525` |
| Background (layer 1) | `gray-75` | `#FAFAFA` | `#2C2C2C` |
| Background (layer 2) | `gray-100` | `#F5F5F5` | `#323232` |
| Foreground (text) | `gray-800` | `#4B4B4B` | `#D5D5D5` |
| Foreground (secondary) | `gray-700` | `#6E6E6E` | `#B3B3B3` |
| Foreground (disabled) | `gray-400` | `#CACACA` | `#5C5C5C` |
| Border (default) | `gray-300` | `#E1E1E1` | `#4A4A4A` |
| Border (emphasis) | `gray-400` | `#CACACA` | `#5C5C5C` |
| Accent (default) | `blue-500 / accent-color-900` | `#0D80D8` | `#2A9AF4` |
| Accent (hover) | `blue-600` | `#0265BB` | `#0D80D8` |
| Accent (down) | `blue-700` | `#034D92` | `#0265BB` |
| Negative (default) | `red-600` | `#D31010` | `#FF5C5C` |
| Negative (hover) | `red-700` | `#B40000` | `#EE2323` |
| Notice (default) | `orange-600` | `#D66D00` | `#FFA033` |
| Positive (default) | `green-600` | `#008400` | `#12B812` |
| Informative (default) | `blue-500` | `#0D80D8` | `#2A9AF4` |

### Static Colors (Theme-Independent)
| Token | Value | Usage |
|-------|-------|-------|
| static-white | `#FFFFFF` | Text on colored backgrounds |
| static-black | `#000000` | Text on light backgrounds |
| static-blue-600 | `#0265BB` | Static brand accent |

### Focus Indicator
```css
/* Focus ring — high contrast, accessible */
outline: 2px solid var(--spectrum-focus-indicator-color); /* blue-500 / #0D80D8 */
outline-offset: 2px;
```

---

## Spacing & Sizing

### Base Unit
Spectrum uses a **base-4** spacing system with consistent multiples.

### Spacing Scale
| Token | Value | Rem |
|-------|-------|-----|
| spacing-50 | 2px | 0.125rem |
| spacing-75 | 4px | 0.25rem |
| spacing-100 | 8px | 0.5rem |
| spacing-200 | 12px | 0.75rem |
| spacing-300 | 16px | 1rem |
| spacing-400 | 24px | 1.5rem |
| spacing-500 | 32px | 2rem |
| spacing-600 | 40px | 2.5rem |
| spacing-700 | 48px | 3rem |
| spacing-800 | 64px | 4rem |
| spacing-900 | 80px | 5rem |
| spacing-1000 | 96px | 6rem |

### Component Sizes (Medium Scale — Desktop)
| Token | Value | Usage |
|-------|-------|-------|
| component-height-50 | 16px | Tiny elements |
| component-height-75 | 24px | Small controls |
| component-height-100 | 32px | Default buttons, inputs, dropdowns |
| component-height-200 | 40px | Large buttons |
| component-height-300 | 48px | Touch targets |

### Component Sizes (Large Scale — Touch/Mobile)
| Token | Value | Usage |
|-------|-------|-------|
| component-height-75 | 32px | Small controls |
| component-height-100 | 40px | Default buttons, inputs |
| component-height-200 | 48px | Large buttons |
| component-height-300 | 56px | Touch targets |

### T-Shirt Sizing
Spectrum components come in 5 sizes:
| Size | Token suffix | Medium scale height | Large scale height |
|------|-------------|---------------------|-------------------|
| XS | `-size-xs` | 16px | 24px |
| S | `-size-s` | 24px | 32px |
| M | `-size-m` | 32px | 40px |
| L | `-size-l` | 40px | 48px |
| XL | `-size-xl` | 48px | 56px |

### Icon Sizes
| Size | Medium | Large |
|------|--------|-------|
| XS | 12px | 14px |
| S | 14px | 16px |
| M | 18px | 20px |
| L | 22px | 24px |
| XL | 26px | 30px |
| XXL | 36px | 40px |

---

## Borders & Radius

### Border Radius
| Token | Value | Usage |
|-------|-------|-------|
| corner-radius-75 | 2px | Small inline elements |
| corner-radius-100 | 4px | Buttons, inputs, dropdowns, tags |
| corner-radius-200 | 8px | Cards, panels, dialogs |
| corner-radius-300 | 12px | Large cards, containers |
| corner-radius-400 | 16px | Large panels, popovers |
| corner-radius-pill | 9999px | Pills, badges |
| corner-radius-circle | 50% | Avatars, status dots |

**Important:** Default component radius is `4px`. Cards and dialogs use `8px`. Never exceed `16px` on standard UI elements.

### Border Widths
| Token | Value | Usage |
|-------|-------|-------|
| border-width-100 | 1px | Default borders, inputs, dividers |
| border-width-200 | 2px | Focus rings, active states, emphasis |
| border-width-400 | 4px | Strong emphasis, selected tab indicator |

### Border Colors (Light Theme)
| Role | Token | Value |
|------|-------|-------|
| Default | `gray-300` | `#E1E1E1` |
| Emphasis / Input | `gray-400` | `#CACACA` |
| Strong / Hover | `gray-500` | `#B3B3B3` |
| Focus | `blue-500` | `#0D80D8` |
| Negative | `red-600` | `#D31010` |
| Disabled | `gray-200` | `#EAEAEA` |

---

## Shadows & Elevation

### Drop Shadows
| Token | Value | Usage |
|-------|-------|-------|
| shadow-100 | `0 1px 4px rgba(0, 0, 0, 0.12)` | Subtle elevation, cards at rest |
| shadow-200 | `0 4px 8px rgba(0, 0, 0, 0.12)` | Floating elements, dropdowns |
| shadow-300 | `0 8px 16px rgba(0, 0, 0, 0.16)` | Popovers, tooltips |
| shadow-400 | `0 12px 24px rgba(0, 0, 0, 0.16)` | Dialogs, modals |
| shadow-500 | `0 16px 32px rgba(0, 0, 0, 0.20)` | Top-level overlays |

**Note:** Spectrum shadows are directional (downward Y-offset), unlike Modus which uses uniform spread.

### Dark Mode Shadows
In dark themes, shadows use higher opacity:
```css
/* Dark theme equivalent */
shadow-100: 0 1px 4px rgba(0, 0, 0, 0.28);
shadow-200: 0 4px 8px rgba(0, 0, 0, 0.28);
shadow-300: 0 8px 16px rgba(0, 0, 0, 0.32);
shadow-400: 0 12px 24px rgba(0, 0, 0, 0.32);
shadow-500: 0 16px 32px rgba(0, 0, 0, 0.36);
```

### Opacity
| Token | Value | Usage |
|-------|-------|-------|
| opacity-disabled | 0.38 | Disabled components |
| opacity-overlay | 0.5 | Backdrop overlay |
| opacity-hover | 0.07 | Hover state overlay (black) |
| opacity-down | 0.12 | Pressed state overlay (black) |

---

## Component Patterns

### Buttons
```css
/* Accent (Primary) — Filled */
background: var(--spectrum-accent-color-900); /* #0D80D8 */
color: #FFFFFF;
border: none;
border-radius: 4px; /* corner-radius-100 */
height: 32px; /* component-height-100, medium */
padding: 0 16px; /* spacing-300 */
font-size: 14px;
font-weight: 700;

/* Accent — Hover */
background: var(--spectrum-accent-color-1000); /* #0265BB */

/* Accent — Active/Down */
background: var(--spectrum-accent-color-1100); /* #034D92 */

/* Accent — Outline variant */
background: transparent;
border: 2px solid var(--spectrum-accent-color-900); /* #0D80D8 */
color: var(--spectrum-accent-color-900);

/* Primary (standard) — Filled */
background: var(--spectrum-gray-800); /* #4B4B4B */
color: var(--spectrum-gray-50); /* #FFFFFF */

/* Secondary — Outline */
background: transparent;
border: 2px solid var(--spectrum-gray-800);
color: var(--spectrum-gray-800);

/* Negative — Filled */
background: var(--spectrum-negative-color-900); /* #D31010 */
color: #FFFFFF;

/* Disabled (all variants) */
opacity: 0.38;
pointer-events: none;

/* Focus (all variants) */
outline: 2px solid var(--spectrum-focus-indicator-color); /* #0D80D8 */
outline-offset: 2px;

/* Transition */
transition: background 130ms ease-out, border-color 130ms ease-out, color 130ms ease-out;
```

#### Button Sizes
| Size | Height (Medium) | Height (Large) | Padding-x | Font Size |
|------|-----------------|----------------|-----------|-----------|
| S | 24px | 32px | 12px | 12px |
| M (default) | 32px | 40px | 16px | 14px |
| L | 40px | 48px | 20px | 16px |
| XL | 48px | 56px | 24px | 18px |

### Cards
```css
background: var(--spectrum-gray-50); /* #FFFFFF */
border: 1px solid var(--spectrum-gray-200); /* #EAEAEA */
border-radius: 8px; /* corner-radius-200 */
overflow: hidden;
padding: 0; /* content manages padding */

/* Card body padding */
padding: 16px 16px; /* spacing-300 */

/* Hover */
border-color: var(--spectrum-gray-400); /* #CACACA */
box-shadow: 0 4px 8px rgba(0, 0, 0, 0.12); /* shadow-200 */

/* Selected */
border: 2px solid var(--spectrum-accent-color-900); /* #0D80D8 */

/* Quiet variant (no border) */
border: none;
background: transparent;
```

### Tables
```css
/* Header */
background: var(--spectrum-gray-75); /* #FAFAFA */
color: var(--spectrum-gray-800); /* #4B4B4B */
font-size: 11px;
font-weight: 700;
text-transform: uppercase;
letter-spacing: 0.06em;
padding: 10px 16px;

/* Row */
background: var(--spectrum-gray-50); /* #FFFFFF */
border-bottom: 1px solid var(--spectrum-gray-200); /* #EAEAEA */
padding: 10px 16px;
font-size: 14px;

/* Row hover */
background: var(--spectrum-gray-75); /* #FAFAFA */

/* Row selected */
background: rgba(13, 128, 216, 0.1); /* blue-500 at 10% */

/* Compact variant */
padding: 6px 16px;

/* Spacious variant */
padding: 14px 16px;

/* Dividers */
border-bottom: 1px solid var(--spectrum-gray-200);
```

### Text Fields (Inputs)
```css
/* Default */
background: var(--spectrum-gray-50); /* #FFFFFF */
border: 1px solid var(--spectrum-gray-400); /* #CACACA */
border-radius: 4px; /* corner-radius-100 */
height: 32px; /* component-height-100 */
padding: 0 12px;
font-size: 14px;
color: var(--spectrum-gray-800); /* #4B4B4B */

/* Hover */
border-color: var(--spectrum-gray-500); /* #B3B3B3 */

/* Focus */
border-color: var(--spectrum-accent-color-900); /* #0D80D8 */
border-width: 2px;

/* Invalid */
border-color: var(--spectrum-negative-color-900); /* #D31010 */

/* Disabled */
background: var(--spectrum-gray-100); /* #F5F5F5 */
border-color: var(--spectrum-gray-200); /* #EAEAEA */
color: var(--spectrum-gray-500); /* #B3B3B3 */
opacity: 0.38;

/* Placeholder */
color: var(--spectrum-gray-600); /* #8E8E8E */

/* Label */
font-size: 12px;
font-weight: 700;
color: var(--spectrum-gray-700); /* #6E6E6E */
margin-bottom: 4px;

/* Help text */
font-size: 12px;
color: var(--spectrum-gray-600); /* #8E8E8E */
margin-top: 4px;
```

### Action Bar / Toolbar
```css
background: var(--spectrum-gray-50);
height: 48px;
padding: 0 16px;
display: flex;
align-items: center;
gap: 8px;
border-bottom: 1px solid var(--spectrum-gray-200);
```

### Tabs
```css
/* Tab item */
font-size: 14px;
font-weight: 700;
color: var(--spectrum-gray-700); /* #6E6E6E */
padding: 10px 16px;
height: 46px;
border-bottom: 2px solid transparent;

/* Selected */
color: var(--spectrum-gray-900); /* #2C2C2C */
border-bottom: 2px solid var(--spectrum-accent-color-900); /* #0D80D8 */

/* Hover */
color: var(--spectrum-gray-900);

/* Compact */
font-size: 12px;
padding: 8px 12px;
```

### Dialogs / Modals
```css
background: var(--spectrum-gray-50); /* #FFFFFF */
border-radius: 8px; /* corner-radius-200 */
box-shadow: 0 12px 24px rgba(0, 0, 0, 0.16); /* shadow-400 */
padding: 32px;
max-width: 480px; /* small */
/* Medium: max-width: 640px */
/* Large: max-width: 864px */

/* Backdrop */
background: rgba(0, 0, 0, 0.5);

/* Dialog title */
font-size: 18px;
font-weight: 700;
margin-bottom: 16px;

/* Dialog footer */
display: flex;
justify-content: flex-end;
gap: 8px;
margin-top: 32px;
```

### Tooltips
```css
background: var(--spectrum-gray-800); /* #4B4B4B (light) */
color: var(--spectrum-gray-50); /* #FFFFFF */
border-radius: 4px;
padding: 4px 8px;
font-size: 12px;
max-width: 200px;
box-shadow: 0 4px 8px rgba(0, 0, 0, 0.12);
```

### Alerts / Toast Notifications
```css
/* Informative (blue) */
background: var(--spectrum-informative-background-color-default);
border-left: 4px solid var(--spectrum-blue-600); /* #0265BB */
border-radius: 4px;
padding: 16px;
color: var(--spectrum-gray-800);

/* Positive (green) */
border-left-color: var(--spectrum-green-600); /* #008400 */

/* Notice / Warning (orange) */
border-left-color: var(--spectrum-orange-600); /* #D66D00 */

/* Negative (red) */
border-left-color: var(--spectrum-red-600); /* #D31010 */

/* Toast (floating) */
background: var(--spectrum-gray-800); /* dark bg */
color: #FFFFFF;
border-radius: 4px;
padding: 12px 16px;
box-shadow: 0 8px 16px rgba(0, 0, 0, 0.16);
```

### Tags / Badges / Labels
```css
/* Tag */
height: 24px;
padding: 0 8px;
border-radius: 4px;
font-size: 12px;
font-weight: 700;
border: 1px solid var(--spectrum-gray-400);
background: transparent;
color: var(--spectrum-gray-800);

/* Badge (status dot) */
width: 8px; height: 8px;
border-radius: 50%;
/* Colors match semantic: positive, negative, notice, informative */

/* Status Light (label + dot) */
font-size: 12px;
font-weight: 700;
display: flex;
align-items: center;
gap: 8px;
```

### Checkboxes & Radios
```css
/* Checkbox */
width: 14px; height: 14px;
border: 2px solid var(--spectrum-gray-600); /* #8E8E8E */
border-radius: 2px;

/* Checked */
background: var(--spectrum-accent-color-900); /* #0D80D8 */
border-color: var(--spectrum-accent-color-900);
/* White checkmark icon */

/* Radio */
width: 14px; height: 14px;
border: 2px solid var(--spectrum-gray-600);
border-radius: 50%;

/* Selected */
border-color: var(--spectrum-accent-color-900);
/* Inner dot: 6px, accent color */

/* Focus (both) */
outline: 2px solid var(--spectrum-focus-indicator-color);
outline-offset: 2px;
```

### Switch / Toggle
```css
/* Track */
width: 26px; height: 14px;
border-radius: 7px;
background: var(--spectrum-gray-400); /* #CACACA */

/* Handle */
width: 14px; height: 14px;
border-radius: 50%;
background: var(--spectrum-gray-75); /* #FAFAFA */
box-shadow: 0 1px 4px rgba(0, 0, 0, 0.12);

/* Checked track */
background: var(--spectrum-accent-color-900); /* #0D80D8 */

/* Transition */
transition: all 130ms ease-out;
```

### Accordion
```css
/* Header */
padding: 12px 16px;
font-size: 14px;
font-weight: 700;
border-top: 1px solid var(--spectrum-gray-200);
cursor: pointer;

/* Content */
padding: 0 16px 16px;
font-size: 14px;

/* Chevron icon rotation */
transition: transform 130ms ease-out;
```

### Breadcrumbs
```css
font-size: 14px;
color: var(--spectrum-gray-700);
/* Separator: ">" or "/" in gray-400 */
/* Current page: font-weight 700, color gray-900 */
/* Link: color accent-color-900 */
```

### Progress Bar
```css
/* Track */
height: 4px; /* S */, 8px; /* M */, 12px; /* L */
background: var(--spectrum-gray-200);
border-radius: 4px;

/* Fill */
background: var(--spectrum-accent-color-900); /* #0D80D8 */
border-radius: 4px;
```

### Avatar
```css
/* Sizes */
/* 50: 16px, 75: 20px, 100: 24px, 200: 28px, 300: 32px,
   400: 36px, 500: 40px, 600: 44px, 700: 48px */
border-radius: 50%;
object-fit: cover;
```

### Side Navigation
```css
/* Item */
padding: 8px 16px;
font-size: 14px;
color: var(--spectrum-gray-800);
border-radius: 4px;

/* Hover */
background: var(--spectrum-gray-200);

/* Selected */
background: var(--spectrum-gray-200);
font-weight: 700;

/* Multi-level indent: 16px per level */
```

---

## Themes

### Four Color Themes
Spectrum supports four built-in themes. Apply via CSS class or attribute:

```html
<!-- Via class -->
<div class="spectrum spectrum--lightest">...</div>
<div class="spectrum spectrum--light">...</div>
<div class="spectrum spectrum--dark">...</div>
<div class="spectrum spectrum--darkest">...</div>

<!-- Via Spectrum CSS custom properties -->
<div data-color="light">...</div>
```

### Theme Token Mapping
| Property | Lightest | Light | Dark | Darkest |
|----------|----------|-------|------|---------|
| Page bg | `#FFFFFF` | `#F5F5F5` | `#323232` | `#1A1A1A` |
| Surface bg | `#FAFAFA` | `#FFFFFF` | `#3E3E3E` | `#252525` |
| Body text | `#4B4B4B` | `#4B4B4B` | `#D5D5D5` | `#EFEFEF` |
| Secondary text | `#6E6E6E` | `#6E6E6E` | `#B3B3B3` | `#A2A2A2` |
| Accent | `#0D80D8` | `#0D80D8` | `#2A9AF4` | `#2A9AF4` |
| Negative | `#D31010` | `#D31010` | `#FF5C5C` | `#FF5C5C` |
| Border | `#E1E1E1` | `#D5D5D5` | `#5C5C5C` | `#494949` |
| Disabled text | `#CACACA` | `#B8B8B8` | `#5C5C5C` | `#494949` |
| Input bg | `#FFFFFF` | `#FFFFFF` | `#3E3E3E` | `#252525` |
| Card bg | `#FFFFFF` | `#FFFFFF` | `#3E3E3E` | `#2C2C2C` |
| Focus ring | `#0D80D8` | `#0D80D8` | `#2A9AF4` | `#2A9AF4` |

### Two Scale Modes
```html
<!-- Desktop density -->
<div class="spectrum spectrum--medium">...</div>

<!-- Touch/mobile density -->
<div class="spectrum spectrum--large">...</div>
```

| Property | Medium (Desktop) | Large (Touch) |
|----------|-------------------|---------------|
| Default component height | 32px | 40px |
| Min touch target | 24px | 40px |
| Default font size | 14px | 16px |
| Icon default | 18px | 20px |
| Input padding-x | 12px | 16px |
| Spacing base | 8px | 8px |

---

## Data Visualization Colors

### Categorical Palette (for charts — use in order)
```
#2680EB  — Blue
#E68619  — Orange
#55B73E  — Green
#DF3D83  — Magenta
#7F84E8  — Indigo
#26B5CE  — Cyan
#F5D000  — Yellow
#CB5DE0  — Purple
#EF6F52  — Red-Orange
#72B332  — Chartreuse
#4EC3A6  — Seafoam
#E26BD7  — Fuchsia
```

### Extended Categorical (12+ series)
For more than 6 series, use lighter/darker variants:
```
Series 1:  #2680EB (blue)     / #1B5EB5 (dark)     / #72B3FF (light)
Series 2:  #E68619 (orange)   / #B5680F (dark)      / #FFB94E (light)
Series 3:  #55B73E (green)    / #3D8F2C (dark)      / #82D96E (light)
Series 4:  #DF3D83 (magenta)  / #B02363 (dark)      / #FF6DAD (light)
Series 5:  #7F84E8 (indigo)   / #5A5FC0 (dark)      / #ABB0FF (light)
Series 6:  #26B5CE (cyan)     / #1A8A9E (dark)      / #5AD8EF (light)
```

### Sequential Palette (for heatmaps, gradients)
Blue progression (5 stops):
```
#DEEBFF → #8AB8FF → #2680EB → #1A5FBF → #103B82
```

Single-hue intensity:
```
Light: 10% → 30% → 50% → 70% → 90% opacity of base color
```

### Diverging Palette (for comparisons)
```
Negative ← → Positive
#D31010 → #FF5C5C → #EAEAEA → #51D351 → #008400
(red)     (light red) (neutral) (light green) (green)
```

### Semantic Data Colors
| Meaning | Color | Hex |
|---------|-------|-----|
| Positive / Up | Green | `#55B73E` |
| Negative / Down | Red | `#EE2323` |
| Warning / Caution | Orange | `#E68619` |
| Neutral / Reference | Gray | `#8E8E8E` |
| Highlight / Selected | Blue | `#2680EB` |

### Chart Styling Rules
- Chart background: transparent (no fills behind chart area)
- Gridlines: `gray-200` (`#EAEAEA` light, `#3E3E3E` dark), dashed or solid 1px
- Axis lines: `gray-300` (`#E1E1E1`), 1px solid
- Axis labels: `gray-700` (`#6E6E6E`), 11px, font-weight 400
- Data labels: `gray-800` (`#4B4B4B`), 12px, font-weight 700
- Titles: `gray-900` (`#2C2C2C`), 14px, font-weight 700
- Legends: `gray-700`, 12px, 8px spacing between items
- Use `tabular-nums` on all numeric labels
- Minimum contrast: 3:1 for data colors against background
- Line chart stroke width: 2px
- Bar corner radius: 2px top corners only

---

## Layout Patterns

### Application Frame
```
+------------------------------------------+
| Toolbar / Top Nav (48px)                 |
+--------+---------------------------------+
| Rail   | Content Area                    |
| (48px  | (scrollable)                    |
| or     |                                 |
| 256px) |                                 |
|        |                                 |
+--------+---------------------------------+
```

### App Dimensions
| Element | Value |
|---------|-------|
| Top nav height | 48px (medium) / 56px (large) |
| Rail width (collapsed) | 48px |
| Rail width (expanded) | 256px |
| Side panel (S) | 256px |
| Side panel (M) | 320px |
| Side panel (L) | 400px |
| Minimum content width | 320px |

### Grid & Breakpoints
| Breakpoint | Width | Columns | Margin | Gutter |
|------------|-------|---------|--------|--------|
| XS (mobile) | < 480px | 4 | 16px | 16px |
| S (tablet portrait) | 480–768px | 8 | 24px | 16px |
| M (tablet landscape) | 768–1024px | 12 | 24px | 24px |
| L (desktop) | 1024–1280px | 12 | 32px | 24px |
| XL (wide desktop) | > 1280px | 12 | 40px | 24px |

### Content Area
- Container max-width: varies by breakpoint, up to 1280px
- Section spacing: 32–48px between major sections
- Card grid gap: 16–24px

---

## Interaction States

All interactive elements follow this state model:

| State | Behavior |
|-------|----------|
| Default | Base styling |
| Hover | Slight background darkening or `opacity-hover` (0.07 black overlay) |
| Active/Down | Stronger darkening or `opacity-down` (0.12 black overlay) |
| Focus | `outline: 2px solid #0D80D8; outline-offset: 2px` |
| Disabled | `opacity: 0.38`, no pointer events |
| Selected | Accent background or accent border |
| Invalid | Red border (`#D31010`), red help text |
| Read-only | No border, no hover, text appears static |

### Transition Timing
```css
/* Standard interaction */
transition-duration: 130ms;
transition-timing-function: ease-out;

/* Overlay/panel open */
transition-duration: 200ms;
transition-timing-function: ease-in;

/* Overlay/panel close */
transition-duration: 160ms;
transition-timing-function: ease-out;
```

### Motion / Animation
| Token | Duration | Usage |
|-------|----------|-------|
| animation-duration-0 | 0ms | Instant |
| animation-duration-100 | 130ms | Micro-interactions (hover, press) |
| animation-duration-200 | 200ms | Small transitions (toggle, checkbox) |
| animation-duration-300 | 300ms | Medium transitions (panel slide) |
| animation-duration-400 | 400ms | Large transitions (modal appear) |
| animation-duration-500 | 500ms | Full-screen transitions |

---

## Accessibility

### Contrast Ratios
- Body text (14px+): minimum 4.5:1 (WCAG AA)
- Large text (18px+ or 14px bold): minimum 3:1 (WCAG AA)
- Non-text elements (icons, borders): minimum 3:1
- Focus indicator: minimum 3:1 against adjacent colors

### Focus Management
- All interactive elements must have visible focus indicators
- Focus ring: `2px solid` accent color with `2px` offset
- Focus order follows DOM order
- Skip navigation links for complex layouts

### Touch Targets
- Minimum touch target: 24x24px (medium), 40x40px (large scale)
- Recommended: 32x32px (medium), 44x44px (large)

### ARIA Patterns
- Spectrum components follow WAI-ARIA 1.2 authoring practices
- All components include appropriate `role`, `aria-label`, and state attributes

---

## Quick Implementation Checklist

When building in Spectrum style:

- [ ] Font: Adobe Clean or Source Sans Pro (300, 400, 600, 700)
- [ ] Body text: 14px desktop, 16px mobile
- [ ] Primary accent: `#0D80D8` (light), `#2A9AF4` (dark)
- [ ] Grays: neutral (no blue/warm tint), pure gray scale
- [ ] Border radius: `4px` for controls, `8px` for cards/dialogs
- [ ] Shadows: directional (Y-offset), not uniform
- [ ] Disabled: `opacity: 0.38` (not 0.3 or 0.5)
- [ ] Focus: `outline: 2px solid` with `2px offset` (not box-shadow)
- [ ] Buttons: 32px default height (medium), 700 weight, 4px radius
- [ ] Inputs: `gray-400` border default, accent on focus, 2px focus border
- [ ] Table headers: uppercase, 11px, letter-spacing 0.06em
- [ ] Transitions: 130ms ease-out (micro), 200ms ease-in (panels)
- [ ] Dark mode: invert gray scale, brighten accent colors
- [ ] Touch scale: increase all heights +8px, increase font +2px
- [ ] `tabular-nums` on all numeric data
- [ ] Focus rings, not focus shadows

---

## Spectrum vs. Tailwind Mapping

| Spectrum | Nearest Tailwind | Note |
|----------|-----------------|------|
| gray-50 #FFFFFF | `white` | Spectrum lightest bg is pure white |
| gray-100 #F5F5F5 | `gray-100` | Very close match |
| gray-200 #EAEAEA | `gray-200` | Close match |
| gray-400 #CACACA | `gray-300` | Spectrum 400 ≈ Tailwind 300 |
| gray-600 #8E8E8E | `gray-400` | Lighter than Tailwind gray-500 |
| gray-700 #6E6E6E | `gray-500` | Close match |
| gray-800 #4B4B4B | `gray-600`/`gray-700` | Between Tailwind values |
| gray-900 #2C2C2C | `gray-800` | Close match |
| blue-500 #0D80D8 | `blue-600` | Spectrum accent is medium-dark |
| blue-400 #2A9AF4 | `blue-500` | Dark mode accent |
| red-600 #D31010 | `red-600` | Very close |
| green-600 #008400 | `green-700` | Spectrum green is darker |
| corner-radius-100 4px | `rounded` | Same default |
| corner-radius-200 8px | `rounded-lg` | Cards and dialogs |
| shadow-200 | `shadow-md` | Similar elevation |
| Body 14px | `text-sm` | Desktop default |
| Body 16px | `text-base` | Mobile / reading |
| spacing-300 16px | `p-4` / `gap-4` | Same value |
| spacing-400 24px | `p-6` / `gap-6` | Same value |

### Critical Differences from Tailwind Defaults
1. Grays are pure neutral (no warm/cool tint) — Tailwind's default grays have slight blue tint
2. Focus uses `outline` with offset, not `ring` (box-shadow)
3. Disabled opacity is `0.38`, not Tailwind's default
4. Border radius stays small — `4px` controls, `8px` cards max
5. Shadows are lighter than Tailwind defaults (lower opacity)
6. Accent blue (`#0D80D8`) is between Tailwind `blue-500` and `blue-600`
7. Transitions are faster (130ms vs Tailwind's 150ms default)
8. Body text defaults to 14px on desktop
