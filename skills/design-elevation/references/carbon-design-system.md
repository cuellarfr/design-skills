# IBM Carbon Design System Reference

A comprehensive reference for building interfaces that conform to IBM's Carbon Design System (v11). Use this when the user requests Carbon styling, IBM branding, or when working on IBM products.

Source: [carbondesignsystem.com](https://carbondesignsystem.com) and [@carbon/themes](https://github.com/carbon-design-system/carbon)

---

## Design Philosophy

Carbon is IBM's open-source design system — built for enterprise products across AI, cloud, data, and infrastructure. It prioritizes:

- **Consistency** across IBM's vast product portfolio
- **Accessibility** (WCAG 2.1 AA compliance, IBM Equal Access guidelines)
- **Productive density** for professional, data-heavy workflows
- **The 2x Grid** — every spatial decision derives from a 2px mini-unit grid
- **Four themes** (White, Gray 10, Gray 90, Gray 100) for flexible surface treatment
- **IBM Design Language** — systematic, rational, and expressive

The aesthetic is clean, geometric, and information-dense. Sharp corners, structured grids, and IBM Plex typography define the visual character.

---

## Typography

### Font Families
```css
/* Primary — all UI text */
font-family: 'IBM Plex Sans', 'Helvetica Neue', Arial, sans-serif;

/* Monospace — code, technical data */
font-family: 'IBM Plex Mono', 'Menlo', 'DejaVu Sans Mono', 'Bitstream Vera Sans Mono', Courier, monospace;

/* Serif — editorial, long-form content */
font-family: 'IBM Plex Serif', 'Georgia', Times, serif;
```

When using Google Fonts:
```html
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Sans:wght@300;400;500;600;700&family=IBM+Plex+Mono:wght@400;600&display=swap" rel="stylesheet">
```

### Type Scale
| Token | Size | Line Height | Weight | Use |
|-------|------|-------------|--------|-----|
| `caption-01` | 12px | 16px | 400 | Captions, labels |
| `caption-02` | 12px | 16px | 400 | Captions, helper text |
| `helper-text-01` | 12px | 16px | 400 | Form helper text |
| `helper-text-02` | 14px | 20px | 400 | Helper text |
| `label-01` | 12px | 16px | 400 | Input labels |
| `label-02` | 14px | 20px | 400 | Input labels |
| `body-compact-01` | 14px | 18px | 400 | Compact body text |
| `body-compact-02` | 16px | 22px | 400 | Compact body text |
| `body-01` | 14px | 20px | 400 | Body text (default) |
| `body-02` | 16px | 24px | 400 | Body text |
| `heading-compact-01` | 14px | 18px | 600 | Compact headings |
| `heading-compact-02` | 16px | 22px | 600 | Compact headings |
| `heading-01` | 14px | 20px | 600 | Section headings |
| `heading-02` | 16px | 24px | 600 | Section headings |
| `heading-03` | 20px | 28px | 400 | Page section headings |
| `heading-04` | 28px | 36px | 400 | Page headings |
| `heading-05` | 32px | 40px | 300 | Large headings |
| `heading-06` | 42px | 50px | 300 | Display headings |
| `heading-07` | 54px | 64px | 300 | Hero headings |

### Font Weights
| Weight | Value | Use |
|--------|-------|-----|
| Light | 300 | Large display headings (heading-05+) |
| Regular | 400 | Body text, most content |
| Medium | 500 | Emphasis within body |
| SemiBold | 600 | Headings, labels, buttons |
| Bold | 700 | Rarely used in UI — reserve for marketing |

---

## Color System

### Brand Colors
| Token | Hex | Use |
|-------|-----|-----|
| `blue-60` | `#0f62fe` | **Primary interactive** — buttons, links, focus |
| `blue-70` | `#0043ce` | Primary hover |
| `blue-80` | `#002d9c` | Primary active |
| `blue-20` | `#d0e2ff` | Light blue highlight |
| `blue-40` | `#78a9ff` | Primary on dark backgrounds |
| `blue-10` | `#edf5ff` | Lightest blue background |

### Gray Scale (Cool Gray)
| Token | Hex | Use |
|-------|-----|-----|
| `cool-gray-10` | `#f2f4f8` | Subtle backgrounds |
| `cool-gray-20` | `#dde1e6` | Borders, dividers |
| `cool-gray-30` | `#c1c7cd` | Disabled text on dark |
| `cool-gray-40` | `#a2a9b0` | Placeholder text |
| `cool-gray-50` | `#878d96` | Secondary text (light) |
| `cool-gray-60` | `#697077` | Secondary text |
| `cool-gray-70` | `#4d5358` | Strong secondary |
| `cool-gray-80` | `#343a3f` | Dark surface |
| `cool-gray-90` | `#21272a` | Darker surface |
| `cool-gray-100` | `#121619` | Darkest surface |

### Gray Scale (Neutral Gray)
| Token | Hex |
|-------|-----|
| `gray-10` | `#f4f4f4` |
| `gray-20` | `#e0e0e0` |
| `gray-30` | `#c6c6c6` |
| `gray-40` | `#a8a8a8` |
| `gray-50` | `#8d8d8d` |
| `gray-60` | `#6f6f6f` |
| `gray-70` | `#525252` |
| `gray-80` | `#393939` |
| `gray-90` | `#262626` |
| `gray-100` | `#161616` |

### Semantic / Status Colors
| Role | Token | Hex |
|------|-------|-----|
| Success | `green-40` | `#42be65` |
| Success (dark bg) | `green-60` | `#198038` |
| Warning | `yellow-30` | `#f1c21b` |
| Error / Danger | `red-60` | `#da1e28` |
| Error (dark bg) | `red-50` | `#fa4d56` |
| Info | `blue-60` | `#0f62fe` |
| Purple | `purple-60` | `#8a3ffc` |
| Teal | `teal-60` | `#007d79` |
| Magenta | `magenta-60` | `#d02670` |

### Theme Tokens (White Theme — Default)
| Token | Value | Use |
|-------|-------|-----|
| `background` | `#ffffff` | Page background |
| `background-hover` | `rgba(141,141,141,0.12)` | Interactive bg hover |
| `background-selected` | `rgba(141,141,141,0.20)` | Selected bg |
| `layer-01` | `#f4f4f4` | First layer (cards on white) |
| `layer-02` | `#ffffff` | Second layer (cards on gray-10) |
| `layer-03` | `#f4f4f4` | Third layer |
| `layer-hover-01` | `#e8e8e8` | Layer hover |
| `field-01` | `#f4f4f4` | Input field bg on white |
| `field-02` | `#ffffff` | Input field bg on gray-10 |
| `border-subtle-00` | `#e0e0e0` | Subtle borders |
| `border-subtle-01` | `#e0e0e0` | Subtle borders on layer |
| `border-strong-01` | `#8d8d8d` | Strong borders |
| `border-interactive` | `#0f62fe` | Interactive borders (focus) |
| `text-primary` | `#161616` | Primary text |
| `text-secondary` | `#525252` | Secondary text |
| `text-placeholder` | `#a8a8a8` | Placeholder text |
| `text-disabled` | `rgba(22,22,22,0.25)` | Disabled text |
| `text-on-color` | `#ffffff` | Text on colored bg |
| `link-primary` | `#0f62fe` | Link color |
| `link-visited` | `#8a3ffc` | Visited links |
| `icon-primary` | `#161616` | Primary icons |
| `icon-secondary` | `#525252` | Secondary icons |
| `icon-disabled` | `rgba(22,22,22,0.25)` | Disabled icons |
| `focus` | `#0f62fe` | Focus outline |
| `interactive` | `#0f62fe` | Interactive elements |

### Theme Tokens (Gray 100 — Dark)
| Token | Value |
|-------|-------|
| `background` | `#161616` |
| `layer-01` | `#262626` |
| `layer-02` | `#393939` |
| `field-01` | `#262626` |
| `border-subtle-01` | `#393939` |
| `border-strong-01` | `#6f6f6f` |
| `text-primary` | `#f4f4f4` |
| `text-secondary` | `#c6c6c6` |
| `text-placeholder` | `#6f6f6f` |
| `link-primary` | `#78a9ff` |
| `icon-primary` | `#f4f4f4` |
| `focus` | `#ffffff` |
| `interactive` | `#4589ff` |

---

## Spacing

Carbon uses a **2x grid** system — all spacing derives from multiples of 2px, with the primary scale at 8px intervals.

### Spacing Scale
| Token | Value | Use |
|-------|-------|-----|
| `spacing-01` | 2px (0.125rem) | Tight icon gaps |
| `spacing-02` | 4px (0.25rem) | Compact spacing |
| `spacing-03` | 8px (0.5rem) | **Base unit** — default gap |
| `spacing-04` | 12px (0.75rem) | Component internal padding |
| `spacing-05` | 16px (1rem) | Standard component padding |
| `spacing-06` | 24px (1.5rem) | Section padding |
| `spacing-07` | 32px (2rem) | Large section spacing |
| `spacing-08` | 40px (2.5rem) | Layout spacing |
| `spacing-09` | 48px (3rem) | Major section breaks |
| `spacing-10` | 64px (4rem) | Page-level spacing |
| `spacing-11` | 80px (5rem) | Hero spacing |
| `spacing-12` | 96px (6rem) | Maximum spacing |
| `spacing-13` | 160px (10rem) | Extra-large layout spacing |

### Container Spacing
| Token | Value | Use |
|-------|-------|-----|
| `container-01` | 24px | Small containers |
| `container-02` | 32px | Default containers |
| `container-03` | 40px | Medium containers |
| `container-04` | 48px | Large containers |
| `container-05` | 64px | Extra-large containers |

---

## Borders & Radius

### Border Radius
Carbon is distinctive for its **sharp corners**:

| Token | Value | Use |
|-------|-------|-----|
| Default | `0` | Buttons, inputs, cards, dropdowns, tiles |
| `border-radius-sm` | `2px` | Tags, badges, small elements |
| `border-radius-md` | `4px` | Tooltips, popovers |
| `border-radius-lg` | `8px` | Modals, notifications (v11+) |
| Pill | `9999px` | Toggle pills |

**Key distinction**: Unlike most design systems, Carbon uses **0px border-radius by default** for most components. This gives IBM products their characteristic angular, structured look.

### Border Widths
| Value | Use |
|-------|-----|
| `1px` | Standard borders, dividers |
| `2px` | Focus rings (inset) |
| `3px` | Strong emphasis borders |

---

## Shadows

Carbon uses minimal shadow — preferring border and layer color to create depth.

| Token | Value | Use |
|-------|-------|-----|
| `shadow-sm` | `0 2px 6px 0 rgba(0,0,0,0.3)` | Small raised elements |
| `shadow-md` | `0 2px 6px 0 rgba(0,0,0,0.3)` | Dropdowns, tooltips |
| `shadow-lg` | `0 8px 24px 0 rgba(0,0,0,0.15)` | Modals, dialogs |
| Overflow shadow | `0 4px 8px 0 rgba(0,0,0,0.25)` | Scrollable overflow |

**Key distinction**: Carbon relies on layer tokens (`layer-01`, `layer-02`, `layer-03`) rather than shadows for most elevation hierarchy.

---

## Component Patterns

### Buttons
| Variant | Background | Text | Border |
|---------|-----------|------|--------|
| Primary | `#0f62fe` (blue-60) | `#ffffff` | none |
| Secondary | `#393939` (gray-80) | `#ffffff` | none |
| Tertiary | transparent | `#0f62fe` | `1px solid #0f62fe` |
| Ghost | transparent | `#0f62fe` | none |
| Danger | `#da1e28` (red-60) | `#ffffff` | none |
| Danger tertiary | transparent | `#da1e28` | none |
| Danger ghost | transparent | `#da1e28` | none |

**Button sizes:**
| Size | Height | Padding | Font |
|------|--------|---------|------|
| Small (sm) | 32px | 0 60px 0 12px | 14px |
| Medium (md) | 40px | 0 60px 0 12px | 14px |
| Large (lg) | 48px | 0 64px 0 16px | 14px |
| Extra-large (xl) | 64px | 0 64px 0 16px | 14px |
| 2XL | 80px | 0 64px 0 16px | 14px |

**Note**: Carbon buttons are wider than most — they include icon space on the right side and use full-width in many contexts.

### Tiles (Cards)
```css
/* Clickable tile */
background: var(--layer-01); /* #f4f4f4 on white theme */
border: none;
border-radius: 0;
padding: 16px;
min-height: 64px;

/* Tile hover */
background: var(--layer-hover-01); /* #e8e8e8 */

/* Selected tile */
border: 1px solid var(--border-interactive); /* #0f62fe */
```

### Data Tables
```css
/* Table header */
background: var(--layer-accent-01); /* #e0e0e0 */
color: var(--text-primary); /* #161616 */
font-size: 14px;
font-weight: 600;
padding: 16px;
height: 48px;

/* Table row */
background: var(--layer-01); /* #f4f4f4 */
border-bottom: 1px solid var(--border-subtle-01);
height: 48px; /* default, also 24/32/40/64px sizes */
padding: 16px;
font-size: 14px;

/* Row hover */
background: var(--layer-hover-01); /* #e8e8e8 */

/* Row selected */
background: var(--layer-selected-01); /* rgba(141,141,141,0.20) */
```

### Text Inputs
```css
/* Default input */
background: var(--field-01); /* #f4f4f4 */
border: none;
border-bottom: 1px solid var(--border-strong-01); /* #8d8d8d */
color: var(--text-primary);
font-size: 14px;
height: 40px; /* default, also 32px sm, 48px lg */
padding: 0 16px;

/* Focus */
outline: 2px solid var(--focus); /* #0f62fe */
outline-offset: -2px;

/* Error */
outline: 2px solid var(--support-error); /* #da1e28 */
```

### Notifications
| Type | Background | Left border |
|------|-----------|-------------|
| Info | `#edf5ff` (blue-10) | `3px solid #0f62fe` |
| Success | `#defbe6` (green-10) | `3px solid #198038` |
| Warning | `#fff8e1` (yellow-10) | `3px solid #f1c21b` |
| Error | `#fff1f1` (red-10) | `3px solid #da1e28` |

### Header / Navigation
```css
/* UI Shell header */
background: #161616; /* Always dark */
height: 48px;
color: #f4f4f4;
font-size: 14px;
font-weight: 600;

/* Side navigation */
background: #ffffff; /* White theme */
width: 256px; /* expanded */
width: 48px; /* collapsed rail */
```

### Tabs
```css
/* Tab (contained) */
background: var(--layer-accent-01); /* #e0e0e0 */
height: 48px;
font-size: 14px;
padding: 0 16px;
border-bottom: none;

/* Selected tab */
background: var(--layer-01);
border-bottom: 2px solid var(--border-interactive);
font-weight: 600;

/* Tab (line) */
border-bottom: 2px solid var(--border-subtle);
/* Selected: border-bottom color changes to interactive */
```

### Tags / Badges
```css
/* Tag */
height: 24px; /* sm: 18px, md: 24px, lg: 32px */
padding: 0 8px;
border-radius: 24px; /* pill shape */
font-size: 12px;
font-weight: 400;

/* Tag colors — high contrast */
/* Red */ background: #fff1f1; color: #a2191f;
/* Blue */ background: #edf5ff; color: #0043ce;
/* Green */ background: #defbe6; color: #0e6027;
/* Purple */ background: #f6f2ff; color: #6929c4;
/* Teal */ background: #d9fbfb; color: #005d5d;
/* Gray */ background: #f4f4f4; color: #525252;
```

### Modals / Dialogs
```css
/* Modal */
background: var(--layer-01);
width: 36%; /* xs: 48%, sm: 60%, lg: 72%, max: 84% */
max-height: 84vh;
box-shadow: 0 8px 24px rgba(0,0,0,0.15);
border-radius: 0; /* Sharp corners */

/* Modal header */
padding: 16px 16px 0;
margin-bottom: 8px;

/* Overlay */
background: rgba(22, 22, 22, 0.5);
```

### Toggle / Switch
```css
/* Toggle off */
background: #8d8d8d;
width: 48px;
height: 24px;
border-radius: 12px;

/* Toggle on */
background: #198038; /* green-60 — not blue! */

/* Small toggle */
width: 32px;
height: 16px;
```

---

## Data Visualization Colors

Carbon has a dedicated data visualization palette:

### Categorical (1-color to 5-color sequences)
```
1 color:  #6929c4 (Purple 70)
2 colors: #6929c4, #1192e8
3 colors: #6929c4, #1192e8, #005d5d
4 colors: #6929c4, #1192e8, #005d5d, #9f1853
5 colors: #6929c4, #1192e8, #005d5d, #9f1853, #fa4d56
```

### Extended palette (14 hues)
```
Purple 70:  #6929c4    Cyan 50:    #1192e8
Teal 70:    #005d5d    Magenta 70: #9f1853
Red 50:     #fa4d56    Red 90:     #570408
Green 60:   #198038    Blue 80:    #002d9c
Magenta 50: #ee5396    Yellow 50:  #b28600
Teal 50:    #009d9a    Cyan 90:    #012749
Purple 50:  #a56eff    Orange 40:  #eb6200
```

### Sequential (single-hue gradient)
```
Blue:  #edf5ff → #d0e2ff → #a6c8ff → #78a9ff → #4589ff → #0f62fe → #0043ce → #002d9c
```

---

## Layout Patterns

### Grid System
Carbon uses a responsive 16-column grid:

| Breakpoint | Columns | Margin | Gutter |
|-----------|---------|--------|--------|
| sm (320px) | 4 | 16px | 32px |
| md (672px) | 8 | 16px | 32px |
| lg (1056px) | 16 | 16px | 32px |
| xl (1312px) | 16 | 16px | 32px |
| max (1584px) | 16 | 24px | 32px |

### UI Shell Dimensions
| Element | Value |
|---------|-------|
| Header height | 48px |
| Side nav width (rail) | 48px |
| Side nav width (expanded) | 256px |
| Footer | Custom (no standard) |
| Content max-width | 1584px |

---

## Interaction States

| State | Visual Treatment |
|-------|-----------------|
| Hover | Background shifts to `layer-hover` token |
| Focus | `2px solid #0f62fe` outline, inset (`outline-offset: -2px`) |
| Active | Background shifts to `layer-active` token |
| Selected | Background uses `layer-selected` + optional blue left border |
| Disabled | 25% opacity on text/icons, non-interactive |
| Visited (links) | `#8a3ffc` (purple-60) |
| Danger hover | `#b81921` (red-70) |

### Motion / Transitions
Carbon defines two motion modes:
| Mode | Duration | Easing | Use |
|------|----------|--------|-----|
| Productive | 70-240ms | `cubic-bezier(0.2, 0, 0.38, 0.9)` | Routine, small transitions |
| Expressive | 150-400ms | `cubic-bezier(0.4, 0.14, 0.3, 1)` | Significant, emphatic transitions |

Common durations:
| Duration token | Value |
|---------------|-------|
| `fast-01` | 70ms |
| `fast-02` | 110ms |
| `moderate-01` | 150ms |
| `moderate-02` | 240ms |
| `slow-01` | 400ms |
| `slow-02` | 700ms |

---

## Quick Implementation Checklist

When building Carbon-styled interfaces:

- [ ] Use IBM Plex Sans (Google Fonts or self-hosted)
- [ ] Set body text to 14px/20px, `#161616`
- [ ] Background: `#ffffff` (White theme) or `#161616` (g100 theme)
- [ ] Primary interactive: `#0f62fe` (Blue 60)
- [ ] Borders: `1px solid #e0e0e0` (subtle) or `#8d8d8d` (strong)
- [ ] **No border-radius** on buttons, inputs, tiles (0px default)
- [ ] Button height: 48px (default), full-width in forms
- [ ] Header: always `#161616`, 48px height
- [ ] Focus: `2px solid #0f62fe`, inset
- [ ] Layer hierarchy: white → gray-10 → white → gray-10 (alternating)
- [ ] 16-column grid, 32px gutters
- [ ] Tabs and toggles use green for "on" state, not blue
- [ ] Tags use pill shape (border-radius: 24px) — exception to no-radius rule
- [ ] Minimal shadows — use layer color shifts for depth

---

## Tailwind CSS Mapping

When translating Carbon tokens to Tailwind:

| Carbon | Tailwind Approximation |
|--------|----------------------|
| IBM Plex Sans 14px | `font-sans text-sm` (customize font-family) |
| `blue-60` (#0f62fe) | `blue-600` (close: #2563eb) — use custom |
| `gray-10` (#f4f4f4) | `gray-100` (#f3f4f6) |
| `gray-80` (#393939) | `gray-700` (#374151) |
| `gray-100` (#161616) | `gray-900` (#111827) — use custom |
| `spacing-05` (16px) | `p-4` |
| `spacing-07` (32px) | `p-8` |
| 0px radius | `rounded-none` |
| 48px button | `h-12` |
| 48px header | `h-12` |
| Focus ring | `ring-2 ring-blue-600 ring-inset` |

**Custom Tailwind config for Carbon:**
```js
// tailwind.config.js
module.exports = {
  theme: {
    extend: {
      fontFamily: {
        sans: ['IBM Plex Sans', 'Helvetica Neue', 'Arial', 'sans-serif'],
        mono: ['IBM Plex Mono', 'Menlo', 'monospace'],
        serif: ['IBM Plex Serif', 'Georgia', 'serif'],
      },
      colors: {
        carbon: {
          blue: { 60: '#0f62fe', 70: '#0043ce', 80: '#002d9c' },
          gray: { 10: '#f4f4f4', 20: '#e0e0e0', 50: '#8d8d8d', 80: '#393939', 100: '#161616' },
          red: { 60: '#da1e28' },
          green: { 60: '#198038' },
          yellow: { 30: '#f1c21b' },
          purple: { 60: '#8a3ffc' },
        }
      },
      borderRadius: {
        none: '0',
      },
      spacing: {
        '0.5': '2px',
      }
    }
  }
}
```
