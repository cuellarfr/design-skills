# Trimble Modus Design System Reference

A comprehensive reference for building interfaces that conform to Trimble's Modus Design System. Use this when the user requests Modus styling, Trimble branding, or when working on Trimble products.

Source: [modus.trimble.com](https://modus.trimble.com) and [modus-web-components](https://github.com/trimble-oss/modus-web-components)

---

## Design Philosophy

Modus is Trimble's shared design system — built for enterprise construction, geospatial, agriculture, and transportation products. It prioritizes:

- **Consistency** across Trimble's product portfolio
- **Accessibility** (WCAG 2.1 AA compliance)
- **Efficiency** for professional, task-heavy workflows
- **Clarity** over decoration — functional, not flashy
- **Light and dark mode** support from the ground up

The aesthetic is professional, utilitarian, and restrained. Think enterprise SaaS for field and office workers — not consumer-facing marketing gloss.

---

## Typography

### Font Family
```css
font-family: 'Open Sans', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto,
  'Helvetica Neue', Arial, 'Noto Sans', sans-serif, 'Apple Color Emoji',
  'Segoe UI Emoji', 'Segoe UI Symbol', 'Noto Color Emoji';
```

When using Google Fonts:
```html
<link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600;700&display=swap" rel="stylesheet">
```

### Type Scale
| Element | Size | Rem | Weight |
|---------|------|-----|--------|
| h1 | 24px | 1.5rem | 700 |
| h2 | 20px | 1.25rem | 700 |
| h3 | 18px | 1.125rem | 700 |
| h4 | 16px | 1rem | 700 |
| h5 | 14px | 0.875rem | 700 |
| h6 | 12px | 0.75rem | 700 |
| Body | 14px | 0.875rem | 400 |
| Small | 12px | 0.75rem | 400 |
| Label | 12px | 0.75rem | 400 |

### Font Weights
- Regular: `400`
- Semi-bold: `600` (buttons, emphasis, tabs, chips, badges)
- Bold: `700` (headings)

### Key Rules
- Body text defaults to 14px, NOT 16px
- Labels are 12px
- Use `font-variant-numeric: tabular-nums` for all data/number displays
- Line height: 1.5 for body, 1.25 for headings

---

## Color System

### Brand Colors
| Name | Hex | Usage |
|------|-----|-------|
| Trimble Blue | `#0063A3` | Primary brand, primary buttons |
| Trimble Blue Dark | `#004F83` | Dark variant, blue navbar bg |
| Trimble Yellow | `#FBAD26` | Warning accent, brand mark |
| Trimble Green | `#349C44` | Brand accent |
| Trimble Red | `#B44E2A` | Brand accent |
| Trimble Gray | `#252A2E` | Dark text, body color, dark bg |

### Gray Scale (Light → Dark)
| Token | Hex | Usage |
|-------|-----|-------|
| Gray Light | `#F1F1F6` | Panel backgrounds, table headers |
| Gray 0 | `#E0E1E9` | Hover states, borders, disabled inputs |
| Gray 1 | `#CBCDD6` | Borders, tertiary button bg, tab borders |
| Gray 2 | `#B7B9C3` | Table borders, disabled text |
| Gray 3 | `#A3A6B1` | Placeholder text, hint text |
| Gray 4 | `#90939F` | Checkbox borders, tertiary icon color |
| Gray 5 | `#7D808D` | Secondary icons |
| Gray 6 | `#6A6E79` | Secondary buttons, input borders, progress borders |
| Gray 7 | `#585C65` | Tooltip bg (light), secondary text |
| Gray 8 | `#464B52` | Input text, table header text, label text |
| Gray 9 | `#353A40` | Card bg (dark), chip text |
| Gray 10 | `#171C1E` | Dark body bg, icon color |

### Blue Progression
| Token | Hex | Usage |
|-------|-----|-------|
| Blue Dark | `#0E416C` | Active/pressed primary, outline active |
| Blue | `#0063A3` | Primary color, links, buttons |
| Blue Light | `#217CBB` | Hover primary, active highlight, links |
| Blue Pale | `#DCEDF9` | Selected bg, hover highlight bg |
| Blue 4 | `#019AEB` | Dark mode primary, highlight accent |

### Semantic Colors
| Role | Light Mode | Dark Mode |
|------|-----------|-----------|
| Primary | `#0063A3` | `#019AEB` |
| Success | `#006638` (green-dark) | `#1E8A44` (green) |
| Warning | `#E49325` (yellow-dark) | `#FBAD26` (yellow) |
| Danger | `#DA212C` (red) | `#DA212C` (red) |
| Secondary | `#6A6E79` (gray-6) | `#6A6E79` |

### Green Progression
| Token | Hex |
|-------|-----|
| Green Dark | `#006638` |
| Green | `#1E8A44` |
| Green Light | `#4EA646` |
| Green Pale | `#E0ECCF` |

### Yellow Progression
| Token | Hex |
|-------|-----|
| Yellow Dark | `#E49325` |
| Yellow | `#FBAD26` |
| Yellow Light | `#FEC157` |
| Yellow Pale | `#FFF5E4` |

### Red Progression
| Token | Hex |
|-------|-----|
| Red Dark | `#AB1F26` |
| Red | `#DA212C` |
| Red Light | `#E86363` |
| Red Pale | `#FBD4D7` |

---

## Spacing & Sizing

### Base Unit
The system uses a **4px base unit** with common values:

| Token | Value |
|-------|-------|
| 1px | 0.0625rem |
| 2px | 0.125rem |
| 4px | 0.25rem |
| 8px | 0.5rem |
| 10px | 0.625rem |
| 12px | 0.75rem |
| 14px | 0.875rem |
| 16px | 1rem |
| 20px | 1.25rem |
| 24px | 1.5rem |
| 32px | 2rem |
| 48px | 3rem |

### Component Heights (3 sizes)
| Size | Height | Padding-x | Font | Icon |
|------|--------|-----------|------|------|
| Small | 24px | 8px | 12px | 16px |
| Default | 32px | 8-16px | 14px | 24px |
| Large | 48px | 12-24px | 16px | 24px |

---

## Borders & Radius

### Border Radius
| Token | Value | Usage |
|-------|-------|-------|
| Default | `4px` (0.25rem) | Buttons, inputs, tooltips, pagination, accordions |
| Small | `2px` (0.125rem) | Progress bars, small elements |
| Large/XL | `8px` (0.5rem) | Cards (cards use `border-radius-xl`) |
| Pill | `1rem` (16px) | Chips |
| Full pill | `50rem` | Badge pills |
| Circle | `50%` | Avatars, profile icons |

**Important:** Most components use `4px`. Cards are the exception at `8px`. Never go larger than 8px on standard components.

### Borders
- Default border: `1px solid`
- Card border: `1px solid #E0E1E9` (gray-0)
- Input border: `1px solid #6A6E79` (gray-6)
- Table border: `1px solid #B7B9C3` (gray-2)
- Active/focus border: `2px solid #217CBB` (blue-light)

---

## Shadows

| Token | Value | Usage |
|-------|-------|-------|
| Small | `0 0 2px rgba(37, 42, 46, 0.3)` | Subtle elevation, focus |
| Default | `0 0 4px rgba(37, 42, 46, 0.3)` | Cards on hover, navbar |
| Large | `0 0 8px rgba(37, 42, 46, 0.3)` | Modals, dropdowns |
| XL | `0 0 16px rgba(37, 42, 46, 0.3)` | Elevated panels |
| XXL | `0 0 24px rgba(37, 42, 46, 0.3)` | Maximum elevation |

Shadow color is based on Trimble Gray `#252A2E` = `rgb(37, 42, 46)`.

**Note:** Modus shadows are uniform (same spread on all sides, no directional offset). This differs from most design systems that use directional shadows.

### Backdrop Blur
| Token | Value |
|-------|-------|
| Small | `blur(4px)` |
| Default | `blur(8px)` |
| Medium | `blur(12px)` |
| Large | `blur(16px)` |
| XL | `blur(24px)` |
| XXL | `blur(40px)` |

---

## Component Patterns

### Buttons
```css
/* Primary */
background: #0063A3; color: #fff; border-radius: 4px;
height: 32px; padding: 0 16px; font-size: 14px; font-weight: 600;

/* Secondary */
background: #6A6E79; color: #fff;

/* Tertiary */
background: #CBCDD6; color: #252A2E;

/* Outline Primary */
background: transparent; border: 1px solid #0063A3; color: #0063A3;

/* Danger */
background: #DA212C; color: #fff;

/* Disabled (all) */
opacity: 0.3; pointer-events: none;

/* Transitions */
transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out,
  border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;

/* Focus */
box-shadow: 0 0 0 0.25rem rgba(0, 99, 163, 0.25);
```

### Cards
```css
background: #fff;
border: 1px solid transparent; /* or #E0E1E9 with .card-border */
border-radius: 4px;
overflow: hidden;
/* Hover shadow on .shadow cards: */
box-shadow: 0 0 4px rgba(54, 53, 69, 0.3);
```

### Navbar
```css
height: 56px;
background: #fff; /* or #0E416C for blue variant */
display: flex; align-items: center;
font-family: 'Open Sans'; font-weight: 600;
/* Profile avatars: 32px, rounded-full */
/* Icons: 12px padding, 4px border-radius */
```

### Tables
```css
/* Header */
background: #F1F1F6; color: #464B52; font-size: 14px;
/* Cells */
padding: 4px 16px; height: 48px (3rem); font-size: 14px; line-height: 1.5;
vertical-align: middle;
/* Small variant */
padding: 4px 8px; height: 32px; font-size: 12px;
/* Borders */
border: 1px solid #B7B9C3;
/* Hover */
background: #DCEDF9;
/* Selected */
background: #DCEDF9; border-color: #217CBB;
```

### Inputs
```css
background: #fff; color: #464B52;
border: 1px solid #6A6E79; border-radius: 4px;
padding: 0 12px; height: 32px; font-size: 14px;
/* Focus */
border-color: #217CBB; border-bottom-width: 2px;
box-shadow: 0 0 2px rgba(36, 35, 45, 0.3);
/* Label */
font-size: 12px; color: #464B52; margin-bottom: 7px;
/* Placeholder */
color: #A3A6B1;
/* Disabled */
background: #E0E1E9; opacity: 0.7;
```

### Tabs
```css
height: 48px; /* 32px small */
padding: 10px 32px; /* 4px 16px small */
font-size: 14px; font-weight: 600;
border-bottom: 1px solid #CBCDD6;
/* Active */
border-bottom: 3px solid #217CBB; color: #217CBB;
/* Hover */
background: #DCEDF9; color: #217CBB;
```

### Badges
```css
font-size: 12px; font-weight: 700;
padding: 4px 8px; border-radius: 4px;
/* Small: 10px font, 2px 4px padding */
/* Large: 16px font, 6px 12px padding */
```

### Alerts
```css
padding: 16px 16px; font-weight: 700;
border-left: 12px solid; border-radius: 4px;
/* Primary: bg rgba(220,237,249,0.5), border #0063A3 */
/* Success: bg rgba(224,236,207,0.5), border #006638 */
/* Danger: bg rgba(251,212,215,0.5), border #DA212C */
/* Warning: bg rgba(255,245,228,0.5), border #E49325 */
```

### Chips
```css
font-size: 13px; font-weight: 600;
border-radius: 1rem; /* pill shape */
padding: 2px 12px;
background: #CBCDD6; color: #353A40;
/* Active: bg rgba(33,124,187,0.3); color: #252A2E */
```

### Accordions
```css
/* Header */
padding: 14px 4px; font-size: 16px; line-height: calc(20/16);
/* Small: 8px 4px padding, 14px font */
/* Border: 1px solid #CBCDD6 */
/* Active border: 1px solid #217CBB */
/* Content: 14px font, 12px small */
```

### Progress Bars
```css
height: 16px;
background: #fff; /* track */
border: 1px solid #6A6E79;
/* Bar fill: #0063A3 (primary) */
```

### Modals
```css
background: #fff; border-radius: 4px;
backdrop: rgba(37, 42, 46, 0.75);
/* Header: height 68px, padding 16px, border-bottom: 1px solid #E0E1E9 */
/* Title: 16px, line-height 1.75 */
/* Footer: same height as header */
```

### Side Navigation
```css
background: #fff;
/* Item hover: bg #E0E1E9 */
/* Item active: bg #217CBB, color: #fff */
/* Disabled: opacity 0.3 */
/* Shadow: 0 0 rgba(0,0,0,0.16) */
```

---

## Dark Mode

Dark mode swaps key tokens:

| Property | Light | Dark |
|----------|-------|------|
| Body bg | `#FFFFFF` | `#252A2E` |
| Body text | `#252A2E` | `#FFFFFF` |
| Primary | `#0063A3` | `#019AEB` |
| Card bg | `#FFFFFF` | `#353A40` |
| Table bg | `#FFFFFF` | `#171C1E` |
| Table header bg | `#F1F1F6` | `#464B52` |
| Input bg | `#FFFFFF` | `#171C1E` |
| Input border | `#6A6E79` | `#464B52` |
| Navbar bg | `#FFFFFF` | `#171C1E` |
| Hover bg | `#E0E1E9` | `#464B52` |
| Selected bg | `#DCEDF9` | `rgba(1,154,235,0.3)` |
| Border color | `#CBCDD6` | `#6A6E79` |
| Shadow color | `rgba(54,53,69,0.3)` | `rgba(23,28,30,0.8)` |

### Dark Mode Implementation
```html
<!-- Apply via data attribute -->
<div data-mwc-theme="dark">...</div>

<!-- Or via class -->
<body class="dark">...</body>
```

---

## Data Visualization Colors

### Categorical Palette (for charts)
Use these in order for multi-series charts:
```
#0063A3  — Blue (primary)
#217CBB  — Blue Light
#006638  — Green Dark
#1E8A44  — Green
#E49325  — Yellow Dark
#FBAD26  — Yellow
#DA212C  — Red
#B44E2A  — Trimble Red
#6A6E79  — Gray 6
#A3A6B1  — Gray 3
```

### Sequential Palette (for heatmaps, gradients)
Blue progression: `#DCEDF9` → `#217CBB` → `#0063A3` → `#0E416C` → `#004F83`

### Semantic Data Colors
- Positive/up: `#006638` (light) / `#1E8A44` (dark)
- Negative/down: `#DA212C`
- Warning/caution: `#E49325` (light) / `#FBAD26` (dark)
- Neutral/reference: `#6A6E79`

### Chart Styling Rules
- Chart background: transparent (no fills)
- Gridlines: `#E0E1E9` (light) or `#464B52` (dark), horizontal only
- Axis labels: `#6A6E79` (gray-6), 12px Open Sans
- Data labels: `#464B52` (gray-8), 12px, semi-bold
- Titles: `#252A2E`, 14px, bold
- Use `tabular-nums` on all number labels

---

## Layout Patterns

### Navbar + Side Nav + Content (Standard App Layout)
```
┌──────────────────────────────────────┐
│ Navbar (56px, full width)            │
├────────┬─────────────────────────────┤
│ Side   │ Content area               │
│ Nav    │ (scrollable)               │
│        │                            │
│        │                            │
└────────┴─────────────────────────────┘
```

### Blue Navbar Variant
For Trimble-branded apps, the navbar can be blue:
```css
background: #0E416C;
color: #fff;
/* Icons and text are white */
```

### App Shell Dimensions
| Element | Value |
|---------|-------|
| Header height | `56px` |
| Sidebar collapsed | `60px` |
| Sidebar expanded | `300px` (at >= 1050px viewport) |
| Footer height | `24px` |
| Toolbar height | `48px` (min), `96px` (max) |
| Panel small | `256px` |
| Panel medium | `352px` |
| Panel large | `448px` |
| Sidebar transition | `flex-basis 0.2s cubic-bezier(0.57, 0.1, 0.73, 1.28)` |

### Grid System
- 12 columns, `24px` gutters (1.5rem)
- Breakpoints: sm 576px, md 768px, lg 992px, xl 1200px, xxl 1600px

### Content Area
- Container padding: 24px (1.5rem)
- Card grid gaps: 16-24px
- Section spacing: 24-32px

---

## Interaction States

All interactive elements follow this state pattern:

| State | Behavior |
|-------|----------|
| Default | Base styling |
| Hover | Background shift (usually gray-0 `#E0E1E9` or blue-pale `#DCEDF9`) |
| Active/Pressed | Darker variant (blue-dark `#0E416C` or gray-7 `#585C65`) |
| Focus | `box-shadow: 0 0 0 0.25rem` with primary color at 25% opacity |
| Disabled | `opacity: 0.3`, no pointer events |
| Selected | Blue pale background `#DCEDF9`, blue-light border `#217CBB` |

Transitions: `0.15s ease-in-out` on color, background-color, border-color, box-shadow.

---

## Quick Implementation Checklist

When building in Modus style:

- [ ] Font: Open Sans (400, 600, 700)
- [ ] Body text: 14px, not 16px
- [ ] Primary blue: `#0063A3`
- [ ] Border radius: `4px` on everything (not 8px, not 12px)
- [ ] Shadows: uniform spread (`0 0 Npx`), not directional
- [ ] Gray scale: use the Modus grays, not Tailwind grays
- [ ] Buttons: 32px height default, 600 weight, 4px radius
- [ ] Navbar: 56px height
- [ ] Tables: gray-light header bg, gray-2 borders
- [ ] Disabled: `opacity: 0.3`
- [ ] Focus rings: `0 0 0 0.25rem` box-shadow
- [ ] Transitions: `0.15s ease-in-out`
- [ ] Inputs: gray-6 border, blue-light on focus, 2px bottom border on focus
- [ ] Labels: 12px, gray-8
- [ ] Alerts: 12px left border, semi-transparent backgrounds
- [ ] `tabular-nums` on all numbers

---

## Modus vs. Tailwind Mapping

For teams familiar with Tailwind, here's how Modus tokens map:

| Modus | Nearest Tailwind | Note |
|-------|-----------------|------|
| Gray Light #F1F1F6 | `gray-100` | Slightly more blue |
| Gray 0 #E0E1E9 | `gray-200` | Modus grays are cooler/bluer |
| Gray 6 #6A6E79 | `gray-500` | |
| Gray 8 #464B52 | `gray-700` | |
| Trimble Gray #252A2E | `gray-800` | |
| Blue #0063A3 | `blue-700` | Modus blue is darker |
| Blue Light #217CBB | `blue-600` | |
| Body 14px | `text-sm` | Modus body is Tailwind's "small" |
| Radius 4px | `rounded` | Not `rounded-lg` |
| Shadow | `shadow-sm` | But uniform, not directional |

**Critical differences from Tailwind defaults:**
1. Body text is 14px (Tailwind default is 16px)
2. Border radius is always 4px (Tailwind's `rounded-lg` 8px is too large)
3. Shadows have no Y-offset (Tailwind shadows are directional)
4. Grays have a cool/blue undertone (Tailwind grays are neutral)
5. Primary blue is darker than Tailwind's blue-600
