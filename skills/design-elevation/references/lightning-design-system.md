# Salesforce Lightning Design System (SLDS) Reference

A comprehensive reference for building interfaces that conform to Salesforce's Lightning Design System. Use this when the user requests SLDS styling, Salesforce branding, Lightning components, or when working on Salesforce platform products.

Source: [lightningdesignsystem.com](https://www.lightningdesignsystem.com) and [@salesforce-ux/design-system](https://github.com/salesforce-ux/design-system)

---

## Design Philosophy

SLDS is Salesforce's design system for enterprise CRM and business applications. It prioritizes:

- **Clarity** — clean, readable interfaces for data-heavy workflows
- **Efficiency** — optimized for productivity across sales, service, marketing, and analytics
- **Consistency** — unified experience across the Salesforce ecosystem
- **Accessibility** — WCAG 2.1 AA compliance throughout
- **Responsiveness** — mobile-first, adaptive layouts
- **Extensibility** — design tokens enable theming across brands and products

The aesthetic is professional, modern, and approachable. Rounded corners, generous whitespace, and a distinctive blue brand color create a friendly enterprise feel that balances data density with visual breathing room.

---

## Typography

### Font Family
```css
font-family: 'Salesforce Sans', Arial, sans-serif;
```

Salesforce Sans is a proprietary font. When unavailable, fall back to:
```css
font-family: Arial, Helvetica, sans-serif;
```

### Font Weights
| Weight | Token | Usage |
|--------|-------|-------|
| Light | `300` | Display headings (optional) |
| Regular | `400` | Body text, labels |
| Bold | `700` | Headings, emphasis |

### Type Scale
| Token | Size | Rem | Usage |
|-------|------|-----|-------|
| `FONT_SIZE_1` | 10px | 0.625rem | Small labels, helper text |
| `FONT_SIZE_2` | 12px | 0.75rem | Labels, badges, metadata |
| `FONT_SIZE_3` | 13px | 0.8125rem | Body small |
| `FONT_SIZE_4` | 14px | 0.875rem | Body default |
| `FONT_SIZE_5` | 16px | 1rem | Body large, subheadings |
| `FONT_SIZE_6` | 18px | 1.125rem | Section headings |
| `FONT_SIZE_7` | 20px | 1.25rem | Page headings |
| `FONT_SIZE_8` | 24px | 1.5rem | Large headings |
| `FONT_SIZE_9` | 28px | 1.75rem | Display headings |
| `FONT_SIZE_10` | 32px | 2rem | Hero headings |
| `FONT_SIZE_11` | 40px | 2.5rem | Display large |

### Line Heights
| Token | Value | Usage |
|-------|-------|-------|
| `LINE_HEIGHT_TEXT` | 1.5 | Body text |
| `LINE_HEIGHT_HEADING` | 1.25 | Headings |
| `LINE_HEIGHT_RESET` | 1 | Icons, buttons |
| `LINE_HEIGHT_TAB` | 2.5rem (40px) | Tab labels |

### Heading Styles
| Element | Size | Weight | Line Height |
|---------|------|--------|-------------|
| Page Title (h1) | 20px (1.25rem) | 700 | 1.25 |
| Card Title (h2) | 16px (1rem) | 700 | 1.25 |
| Section Title (h3) | 14px (0.875rem) | 700 | 1.25 |
| Subsection (h4) | 14px (0.875rem) | 700 | 1.25 |

### Key Rules
- Body text defaults to 13px in the Lightning platform, 14px in standalone
- Labels are 12px, uppercase tracking is NOT used
- Page headers use 20px bold, not larger
- Use `font-variant-numeric: tabular-nums` for data tables and numeric displays
- Letter spacing is generally `normal` (no custom tracking)

---

## Color System

### Brand Colors
| Name | Hex | RGB | Token | Usage |
|------|-----|-----|-------|-------|
| Brand Primary | `#1589EE` | 21, 137, 238 | `COLOR_BRAND` | Links, primary actions |
| Brand Dark | `#0070D2` | 0, 112, 210 | `COLOR_BRAND_DARK` | Primary buttons |
| Brand Darker | `#005FB2` | 0, 95, 178 | `COLOR_BRAND_DARKER` | Hover states |
| Brand Light | `#1B96FF` | 27, 150, 255 | — | Light brand accent |
| Brand Accessible | `#0070D2` | 0, 112, 210 | `BRAND_ACCESSIBLE` | WCAG AA accessible brand |

### Core UI Colors
| Name | Hex | Token | Usage |
|------|-----|-------|-------|
| Page Background | `#F3F3F3` | `COLOR_BACKGROUND` | App background |
| White | `#FFFFFF` | `COLOR_BACKGROUND_ALT` | Cards, modals |
| Dark Background | `#16325C` | `COLOR_BACKGROUND_INVERSE` | Dark surfaces |
| Highlight Row | `#F3F3F3` | `COLOR_BACKGROUND_ROW_HOVER` | Table hover |
| Selected Row | `#EEF1F6` | `COLOR_BACKGROUND_ROW_SELECTED` | Table selected |
| Active Row | `#E2E2E2` | `COLOR_BACKGROUND_ROW_ACTIVE` | Pressed state |

### Gray Palette (Light to Dark)
| Token | Hex | Usage |
|-------|-----|-------|
| `COLOR_GRAY_1` | `#F3F3F3` | Page backgrounds, alt backgrounds |
| `COLOR_GRAY_2` | `#E5E5E5` | Borders, dividers, disabled bg |
| `COLOR_GRAY_3` | `#D9D9D9` | Input borders (disabled) |
| `COLOR_GRAY_4` | `#C9C9C9` | Placeholder text borders |
| `COLOR_GRAY_5` | `#B0B0B0` | Disabled text, placeholder |
| `COLOR_GRAY_6` | `#969696` | Secondary text, icons |
| `COLOR_GRAY_7` | `#706E6B` | Body text (secondary) |
| `COLOR_GRAY_8` | `#514F4D` | Body text (primary) |
| `COLOR_GRAY_9` | `#3E3E3C` | Headings, strong text |
| `COLOR_GRAY_10` | `#2B2826` | Darkest gray text |
| `COLOR_GRAY_11` | `#1A1B1E` | Near-black |
| `COLOR_GRAY_12` | `#080707` | True dark text |
| `COLOR_GRAY_13` | `#000000` | Pure black (rare) |

### Blue Palette
| Token | Hex | Usage |
|-------|-----|-------|
| Blue Lightest | `#EEF4FF` | Selected backgrounds, highlights |
| Blue Lighter | `#D8EDFF` | Hover highlight |
| Blue Light | `#1B96FF` | Links, interactive elements |
| Blue | `#0176D3` | Brand primary standard |
| Blue Dark | `#0070D2` | Primary buttons, actions |
| Blue Darker | `#005FB2` | Button hover |
| Blue Darkest | `#014486` | Button pressed/active |

### Semantic / Alert Colors
| Role | Hex | Token | Usage |
|------|-----|-------|-------|
| Success | `#2E844A` | `COLOR_SUCCESS` | Success states, positive |
| Success Dark | `#194E31` | `COLOR_SUCCESS_DARK` | Success text |
| Success Light | `#45C65A` | — | Success accents |
| Warning | `#DD7A01` | `COLOR_WARNING` | Warning states |
| Warning Dark | `#A96404` | `COLOR_WARNING_DARK` | Warning text |
| Warning Light | `#FE9339` | — | Warning accents |
| Error / Destructive | `#C23934` | `COLOR_ERROR` | Error states, destructive |
| Error Dark | `#8E030F` | `COLOR_ERROR_DARK` | Error text |
| Error Light | `#EA001E` | — | Error accents |
| Info | `#0070D2` | — | Informational (uses brand blue) |

### Text Colors
| Token | Hex | Usage |
|-------|-----|-------|
| `COLOR_TEXT_DEFAULT` | `#080707` | Default body text |
| `COLOR_TEXT_WEAK` | `#706E6B` | Secondary/muted text |
| `COLOR_TEXT_INVERSE` | `#FFFFFF` | Text on dark backgrounds |
| `COLOR_TEXT_PLACEHOLDER` | `#706E6B` | Input placeholders |
| `COLOR_TEXT_LINK` | `#0070D2` | Link text |
| `COLOR_TEXT_LINK_HOVER` | `#005FB2` | Link hover |
| `COLOR_TEXT_ERROR` | `#C23934` | Error messages |
| `COLOR_TEXT_SUCCESS` | `#2E844A` | Success messages |
| `COLOR_TEXT_WARNING` | `#DD7A01` | Warning messages |
| `COLOR_TEXT_LABEL` | `#3E3E3C` | Form labels |
| `COLOR_TEXT_HEADING` | `#080707` | Heading text |

### Border Colors
| Token | Hex | Usage |
|-------|-----|-------|
| `COLOR_BORDER` | `#E5E5E5` | Default border |
| `COLOR_BORDER_INPUT` | `#706E6B` | Input field borders |
| `COLOR_BORDER_INPUT_ACTIVE` | `#0070D2` | Focused input border |
| `COLOR_BORDER_SEPARATOR` | `#E5E5E5` | Dividers, separators |
| `COLOR_BORDER_BRAND` | `#0070D2` | Brand-colored borders |
| `COLOR_BORDER_ERROR` | `#C23934` | Error state borders |
| `COLOR_BORDER_SUCCESS` | `#2E844A` | Success state borders |
| `COLOR_BORDER_WARNING` | `#DD7A01` | Warning state borders |

### Background Variants
| Token | Hex | Usage |
|-------|-----|-------|
| `COLOR_BACKGROUND` | `#F3F3F3` | Page background |
| `COLOR_BACKGROUND_ALT` | `#FFFFFF` | Cards, containers |
| `COLOR_BACKGROUND_ALT_2` | `#F3F3F3` | Alternate rows |
| `COLOR_BACKGROUND_HIGHLIGHT` | `#F3F3F3` | Hover states |
| `COLOR_BACKGROUND_SELECTION` | `#EEF4FF` | Selected items |
| `COLOR_BACKGROUND_STENCIL` | `#E5E5E5` | Loading skeletons |
| `COLOR_BACKGROUND_INVERSE` | `#16325C` | Dark headers |
| `COLOR_BACKGROUND_SUCCESS` | `#2E844A` | Success badge bg |
| `COLOR_BACKGROUND_WARNING` | `#DD7A01` | Warning badge bg |
| `COLOR_BACKGROUND_ERROR` | `#C23934` | Error badge bg |
| `COLOR_BACKGROUND_INFO` | `#0070D2` | Info badge bg |
| `COLOR_BACKGROUND_TOAST_SUCCESS` | `#2E844A` | Success toast |
| `COLOR_BACKGROUND_TOAST_ERROR` | `#C23934` | Error toast |

---

## Spacing & Sizing

### Spacing Scale (4px base unit)
| Token | Value | Rem |
|-------|-------|-----|
| `SPACING_NONE` | 0 | 0 |
| `SPACING_XXX_SMALL` | 2px | 0.125rem |
| `SPACING_XX_SMALL` | 4px | 0.25rem |
| `SPACING_X_SMALL` | 8px | 0.5rem |
| `SPACING_SMALL` | 12px | 0.75rem |
| `SPACING_MEDIUM` | 16px | 1rem |
| `SPACING_LARGE` | 24px | 1.5rem |
| `SPACING_X_LARGE` | 32px | 2rem |
| `SPACING_XX_LARGE` | 48px | 3rem |

### Sizing Tokens
| Token | Value | Usage |
|-------|-------|-------|
| `SIZE_XX_SMALL` | 6rem (96px) | Small panels |
| `SIZE_X_SMALL` | 12rem (192px) | Narrow columns |
| `SIZE_SMALL` | 15rem (240px) | Side panels |
| `SIZE_MEDIUM` | 20rem (320px) | Medium panels |
| `SIZE_LARGE` | 25rem (400px) | Content areas |
| `SIZE_X_LARGE` | 40rem (640px) | Wide content |
| `SIZE_XX_LARGE` | 60rem (960px) | Max content |

### Component Heights
| Size | Height | Token | Usage |
|------|--------|-------|-------|
| XX-Small | 20px | — | Badges, pills |
| X-Small | 24px | — | Small buttons, compact inputs |
| Small | 30px | — | Compact components |
| Medium (Default) | 36px | — | Standard buttons, inputs |
| Large | 44px | — | Touch-friendly targets |

### Square Sizing (Icons & Avatars)
| Token | Value | Usage |
|-------|-------|-------|
| `SQUARE_ICON_UTILITY_SMALL` | 16px | Small utility icons |
| `SQUARE_ICON_UTILITY_MEDIUM` | 20px | Standard utility icons |
| `SQUARE_ICON_UTILITY_LARGE` | 24px | Large utility icons |
| `SQUARE_ICON_SMALL` | 24px | Small standard icons |
| `SQUARE_ICON_MEDIUM` | 32px | Medium standard icons |
| `SQUARE_ICON_LARGE` | 48px | Large standard icons |

---

## Borders & Radius

### Border Radius
| Token | Value | Usage |
|-------|-------|-------|
| `BORDER_RADIUS_SMALL` | 0.125rem (2px) | Small elements, tags |
| `BORDER_RADIUS_MEDIUM` | 0.25rem (4px) | Default — buttons, inputs, cards |
| `BORDER_RADIUS_LARGE` | 0.5rem (8px) | Modals, popovers, large containers |
| `BORDER_RADIUS_CIRCLE` | 50% | Avatars, status indicators |
| `BORDER_RADIUS_PILL` | 15rem | Pills, badges |

**Key rule:** SLDS uses `0.25rem` (4px) as the primary radius. Cards, buttons, inputs, and most components use 4px. Modals and popovers use 8px. Avatars use full circle.

### Border Widths
| Token | Value | Usage |
|-------|-------|-------|
| `BORDER_WIDTH_THIN` | 1px | Standard borders |
| `BORDER_WIDTH_THICK` | 2px | Active/focus indicators |

### Borders
- Default border: `1px solid #E5E5E5`
- Input border: `1px solid #706E6B`
- Input focus: `1px solid #0070D2` + blue shadow
- Table cell border: `1px solid #E5E5E5`
- Card border: `1px solid #E5E5E5`
- Error border: `1px solid #C23934`
- Active indicator: `2px solid #0070D2` (bottom border on tabs, etc.)

---

## Shadows

| Token | Value | Usage |
|-------|-------|-------|
| `SHADOW_SOFT_SMALL` | `0 2px 4px rgba(0,0,0,0.10)` | Subtle elevation (buttons on hover) |
| `SHADOW_SOFT_MEDIUM` | `0 4px 8px rgba(0,0,0,0.10)` | Cards on hover |
| `SHADOW_SOFT_LARGE` | `0 8px 16px rgba(0,0,0,0.10)` | Dropdowns, popovers |
| `SHADOW_DROP_DOWN` | `0 2px 3px 0 rgba(0,0,0,0.16)` | Dropdown menus |
| `SHADOW_BUTTON` | `0 1px 1px 0 rgba(0,0,0,0.05)` | Default button shadow |
| `SHADOW_BUTTON_FOCUS` | `0 0 3px #0070D2` | Button focus ring |
| `SHADOW_OVERLAY` | `0 -2px 4px rgba(0,0,0,0.07)` | Bottom sheets, overlays |
| `SHADOW_MODAL` | `0 2px 8px rgba(0,0,0,0.16)` | Modals, dialogs |
| `SHADOW_DRAG` | `0 2px 4px rgba(0,0,0,0.40)` | Dragged elements |
| `SHADOW_CARD` | `0 2px 2px 0 rgba(0,0,0,0.10)` | Card resting state |
| `SHADOW_HEADER` | `0 2px 4px rgba(0,0,0,0.07)` | Sticky headers |

### Elevation Levels
| Level | Shadow | Usage |
|-------|--------|-------|
| 0 | none | Inline, flat elements |
| 1 | `SHADOW_CARD` | Cards, tiles |
| 2 | `SHADOW_DROP_DOWN` | Dropdowns, menus |
| 3 | `SHADOW_MODAL` | Modals, dialogs |
| 4 | `SHADOW_DRAG` | Dragged items |

### Focus Ring
```css
box-shadow: 0 0 3px #0070D2;
outline: 0;
/* Or using custom focus ring: */
box-shadow: 0 0 0 2px #FFFFFF, 0 0 0 4px #0070D2;
```

---

## Z-Index Scale
| Token | Value | Usage |
|-------|-------|-------|
| `Z_INDEX_DEFAULT` | 1 | Default stacking |
| `Z_INDEX_DIALOG` | 6000 | Dialogs |
| `Z_INDEX_POPUP` | 7000 | Popovers, tooltips |
| `Z_INDEX_MODAL` | 9000 | Modals |
| `Z_INDEX_OVERLAY` | 8000 | Overlays, backdrops |
| `Z_INDEX_SPINNER` | 9050 | Loading spinners |
| `Z_INDEX_TOAST` | 10000 | Toast notifications |
| `Z_INDEX_DOCKED` | 4 | Docked panels |
| `Z_INDEX_STICKY` | 100 | Sticky headers |
| `Z_INDEX_REMINDER` | 8500 | Reminder overlays |

---

## Component Patterns

### Buttons
```css
/* Base Button */
font-family: 'Salesforce Sans', Arial, sans-serif;
font-size: 13px;
line-height: 1.875rem (30px);
height: 2rem (32px);
padding: 0 1rem (0 16px);
border-radius: 0.25rem (4px);
font-weight: 400;
text-align: center;
cursor: pointer;
white-space: nowrap;
transition: border 0.15s linear, background-color 0.15s linear;

/* Neutral (Default) */
background: #FFFFFF;
border: 1px solid #706E6B;
color: #0070D2;

/* Neutral Hover */
background: #F3F3F3;

/* Brand (Primary) */
background: #0070D2;
border: 1px solid #0070D2;
color: #FFFFFF;

/* Brand Hover */
background: #005FB2;
border-color: #005FB2;

/* Brand Active */
background: #014486;
border-color: #014486;

/* Outline Brand */
background: transparent;
border: 1px solid #0070D2;
color: #0070D2;

/* Outline Brand Hover */
background: #F3F3F3;

/* Destructive */
background: #C23934;
border: 1px solid #C23934;
color: #FFFFFF;

/* Destructive Hover */
background: #8E030F;
border-color: #8E030F;

/* Success */
background: #2E844A;
border: 1px solid #2E844A;
color: #FFFFFF;

/* Inverse (on dark bg) */
background: transparent;
border: 1px solid #FFFFFF;
color: #FFFFFF;

/* Disabled (all variants) */
background: #FFFFFF;
border-color: #C9C9C9;
color: #C9C9C9;
cursor: default;
pointer-events: none;

/* Focus (all variants) */
box-shadow: 0 0 3px #0070D2;
outline: 0;

/* Icon-only Button */
width: 2rem (32px);
height: 2rem (32px);
padding: 0;
border-radius: 0.25rem (4px);
/* or border-radius: 50% for circular icon buttons */
```

### Button Sizes
| Size | Height | Font Size | Padding |
|------|--------|-----------|---------|
| Small | 24px | 12px | 0 8px |
| Medium (default) | 32px | 13px | 0 16px |
| Large | 44px | 14px | 0 24px |

### Cards
```css
/* Base Card */
background: #FFFFFF;
border: 1px solid #E5E5E5;
border-radius: 0.25rem (4px);
padding: 0;
box-shadow: 0 2px 2px 0 rgba(0,0,0,0.10);

/* Card Header */
padding: 0.75rem 1rem (12px 16px);
border-bottom: 1px solid #E5E5E5;

/* Card Header Title */
font-size: 1rem (16px);
font-weight: 700;
color: #080707;

/* Card Body */
padding: 0.75rem 1rem (12px 16px);

/* Card Footer */
padding: 0.75rem 1rem (12px 16px);
border-top: 1px solid #E5E5E5;
text-align: center; /* typically for "View All" link */

/* Card (no border variant) */
border: none;
box-shadow: none;
```

### Global Navigation / App Header
```css
/* Global Header */
background: #FFFFFF;
height: 3.125rem (50px);
border-bottom: 3px solid #0070D2;
padding: 0 1rem;
display: flex;
align-items: center;

/* Navigation Bar (App-level) */
background: #FFFFFF;
height: 2.5rem (40px);
border-bottom: 1px solid #E5E5E5;

/* Navigation Bar Item */
padding: 0 1rem;
font-size: 14px;
color: #706E6B;
height: 100%;
display: flex;
align-items: center;

/* Navigation Bar Item Active */
color: #0070D2;
border-bottom: 3px solid #0070D2;

/* Navigation Bar Item Hover */
color: #005FB2;
background: #F3F3F3;

/* App Launcher Icon */
width: 48px;
height: 48px;
background: #0070D2;
border-radius: 4px;
/* 9-dot grid icon in white */
```

### Tabs
```css
/* Tab Container */
border-bottom: 1px solid #E5E5E5;

/* Tab Item */
padding: 0 1rem;
height: 2.5rem (40px);
font-size: 13px;
color: #706E6B;
font-weight: 400;
border-bottom: 2px solid transparent;
cursor: pointer;

/* Tab Item Active */
color: #0070D2;
font-weight: 700;
border-bottom: 2px solid #0070D2;

/* Tab Item Hover */
color: #005FB2;
border-bottom-color: #005FB2;

/* Tab Item Focus */
box-shadow: 0 0 3px #0070D2;

/* Scoped Tabs (enclosed) */
background: #F3F3F3;
border: 1px solid #E5E5E5;
border-radius: 0.25rem 0.25rem 0 0;

/* Scoped Tab Active */
background: #FFFFFF;
border-bottom-color: #FFFFFF;

/* Vertical Tabs */
width: 200px;
border-right: 1px solid #E5E5E5;
/* Item: padding 0.75rem 1rem, border-left: 3px solid transparent */
/* Active: border-left-color: #0070D2 */
```

### Data Tables
```css
/* Table Container */
width: 100%;
background: #FFFFFF;
border: 1px solid #E5E5E5;
border-collapse: separate;
border-spacing: 0;

/* Header */
background: #FAFAF9;
color: #706E6B;
font-size: 12px;
font-weight: 700;
text-transform: uppercase;
letter-spacing: 0.0625em;
padding: 0.25rem 0.5rem (4px 8px);
line-height: 1.25;
border-bottom: 1px solid #E5E5E5;

/* Header Cell */
padding: 0.5rem 0.75rem (8px 12px);
vertical-align: middle;
white-space: nowrap;

/* Body Cell */
padding: 0.5rem 0.75rem (8px 12px);
font-size: 13px;
color: #080707;
border-top: 1px solid #E5E5E5;
vertical-align: middle;
line-height: 1.5;

/* Row Hover */
background: #F3F3F3;

/* Row Selected */
background: #EEF4FF;

/* Row Active */
background: #E2E2E2;

/* Striped Rows (alternate) */
background: #FAFAF9;

/* Column Sorting Indicator */
/* Arrow icon, 8px, appended to header text */

/* Cell Actions on Hover */
/* Revealed on row hover, right-aligned dropdown */

/* Compact Table */
/* Cell padding: 0.25rem 0.5rem (4px 8px) */

/* Inline Edit */
/* Cell becomes input on click, blue focus border */

/* Resizable Columns */
/* Drag handle: 2px width, #0070D2 on drag */
```

### Inputs
```css
/* Base Input */
background: #FFFFFF;
color: #080707;
border: 1px solid #706E6B;
border-radius: 0.25rem (4px);
padding: 0 0.75rem (0 12px);
height: 2rem (32px);
font-size: 13px;
line-height: 1.875rem;
width: 100%;
transition: border 0.1s linear, background-color 0.1s linear;

/* Input Focus */
border-color: #0070D2;
box-shadow: 0 0 3px #0070D2;
outline: 0;

/* Input Disabled */
background: #E5E5E5;
border-color: #C9C9C9;
color: #706E6B;
cursor: not-allowed;

/* Input Read-Only */
border-color: transparent;
background: transparent;
padding-left: 0;

/* Input Error */
border-color: #C23934;
box-shadow: #C23934 0 0 0 1px inset;
background: #FEF1F1;

/* Label */
font-size: 0.75rem (12px);
color: #3E3E3C;
font-weight: 400;
margin-bottom: 0.125rem (2px);
display: block;

/* Required Indicator */
color: #C23934;
/* Asterisk (*) before label text */

/* Help Text */
font-size: 11px;
color: #706E6B;
margin-top: 0.125rem;

/* Error Message */
font-size: 12px;
color: #C23934;
margin-top: 0.125rem;

/* Placeholder */
color: #706E6B;

/* Textarea */
min-height: 5rem (80px);
padding: 0.5rem 0.75rem;
resize: vertical;

/* Select */
appearance: none;
background-image: url(down-arrow-icon);
background-position: right 0.75rem center;
padding-right: 2rem;
```

### Input Sizes
| Size | Height | Font Size | Padding |
|------|--------|-----------|---------|
| Small | 24px | 12px | 0 8px |
| Default | 32px | 13px | 0 12px |
| Large | 40px | 14px | 0 16px |

### Checkbox & Radio
```css
/* Checkbox/Radio Container */
display: flex;
align-items: center;
gap: 0.5rem;

/* Custom Checkbox */
width: 1rem (16px);
height: 1rem (16px);
border: 1px solid #706E6B;
border-radius: 0.125rem (2px); /* checkbox */
border-radius: 50%; /* radio */
background: #FFFFFF;

/* Checked */
background: #0070D2;
border-color: #0070D2;
/* White checkmark/dot inside */

/* Focus */
box-shadow: 0 0 3px #0070D2;

/* Disabled */
background: #E5E5E5;
border-color: #C9C9C9;
```

### Toggle / Switch
```css
/* Track */
width: 3rem (48px);
height: 1.5rem (24px);
border-radius: 15rem;
background: #706E6B;

/* Track Active */
background: #0070D2;

/* Thumb */
width: 1.25rem (20px);
height: 1.25rem (20px);
border-radius: 50%;
background: #FFFFFF;
box-shadow: 0 1px 2px rgba(0,0,0,0.2);
transform: translateX(0); /* off */
transform: translateX(1.5rem); /* on */
transition: transform 0.2s ease;

/* Disabled */
opacity: 0.5;
```

### Badges & Pills
```css
/* Badge */
font-size: 12px;
font-weight: 700;
padding: 2px 8px;
border-radius: 15rem; /* pill shape */
color: #FFFFFF;
display: inline-block;

/* Badge Variants */
/* Default: */ background: #706E6B;
/* Success: */ background: #2E844A;
/* Warning: */ background: #DD7A01;
/* Error: */   background: #C23934;
/* Info: */    background: #0070D2;
/* Inverse: */ background: #16325C;
/* Light: */   background: #F3F3F3; color: #080707;

/* Pill (removable tag) */
background: #FFFFFF;
border: 1px solid #E5E5E5;
border-radius: 15rem;
padding: 0 0.5rem;
height: 1.5rem (24px);
font-size: 12px;
/* Remove button: 16px circle with X icon */
```

### Alerts / Notifications (Toast)
```css
/* Toast Container */
position: fixed;
top: 2.5rem;
left: 50%;
transform: translateX(-50%);
z-index: 10000;
min-width: 30rem;

/* Toast */
border-radius: 0.25rem;
padding: 0.75rem 3rem 0.75rem 1rem;
font-size: 14px;
display: flex;
align-items: flex-start;
gap: 0.75rem;

/* Toast Variants */
/* Success: */ background: #2E844A; color: #FFFFFF;
/* Error: */   background: #C23934; color: #FFFFFF;
/* Warning: */ background: #DD7A01; color: #FFFFFF;
/* Info: */    background: #706E6B; color: #FFFFFF;

/* Close button: absolute right 0.5rem, white icon */
```

### Alert Banners (Inline)
```css
/* Alert */
padding: 0.75rem 3rem 0.75rem 1rem;
border-radius: 0.25rem;
font-size: 13px;
position: relative;

/* Alert Variants (light background) */
/* Info: */    background: #EEF4FF; border-left: 4px solid #0070D2; color: #080707;
/* Warning: */ background: #FFF8E1; border-left: 4px solid #DD7A01; color: #080707;
/* Error: */   background: #FEF1F1; border-left: 4px solid #C23934; color: #080707;
/* Success: */ background: #E6F7E9; border-left: 4px solid #2E844A; color: #080707;
/* Offline: */ background: #3E3E3C; color: #FFFFFF;
```

### Modals
```css
/* Backdrop */
background: rgba(0, 0, 0, 0.8);
z-index: 9000;

/* Modal */
background: #FFFFFF;
border-radius: 0.5rem (8px);
max-width: 50rem;
min-width: 20rem;
z-index: 9001;
box-shadow: 0 2px 8px rgba(0,0,0,0.16);
position: fixed;
top: 50%;
left: 50%;
transform: translate(-50%, -50%);

/* Modal Header */
padding: 1rem;
border-bottom: 1px solid #E5E5E5;
display: flex;
justify-content: space-between;
align-items: center;

/* Modal Title */
font-size: 20px;
font-weight: 700;
color: #080707;

/* Modal Body */
padding: 1rem;
max-height: 70vh;
overflow-y: auto;

/* Modal Footer */
padding: 0.75rem 1rem;
border-top: 1px solid #E5E5E5;
display: flex;
justify-content: flex-end;
gap: 0.5rem;

/* Modal Sizes */
/* Small: max-width 25rem (400px) */
/* Medium: max-width 40rem (640px) */
/* Large: max-width 60rem (960px) */
```

### Popover / Dropdown Menu
```css
/* Popover */
background: #FFFFFF;
border: 1px solid #E5E5E5;
border-radius: 0.25rem (4px);
box-shadow: 0 2px 3px 0 rgba(0,0,0,0.16);
padding: 0.5rem 0;
z-index: 7000;
min-width: 6rem;

/* Nubbin (caret) — CSS triangle */
/* 1rem x 1rem rotated square, positioned on edge */

/* Menu Item */
padding: 0.5rem 0.75rem;
font-size: 13px;
color: #080707;
cursor: pointer;
line-height: 1.5;

/* Menu Item Hover */
background: #F3F3F3;
color: #0070D2;

/* Menu Item Active/Selected */
background: #EEF4FF;
color: #0070D2;

/* Menu Item Disabled */
color: #C9C9C9;
cursor: default;

/* Menu Item Divider */
border-top: 1px solid #E5E5E5;
margin: 0.25rem 0;

/* Menu Item with Icon */
padding-left: 2.5rem;
/* Icon: absolute left 0.75rem, 16px utility icon */
```

### Tooltips
```css
background: #16325C;
color: #FFFFFF;
border-radius: 0.25rem (4px);
padding: 0.5rem 0.75rem;
font-size: 12px;
max-width: 20rem;
z-index: 7000;
/* Nubbin: small triangle pointing to trigger */
```

### Spinners / Loading
```css
/* Spinner */
width: 2rem (32px); /* medium */
height: 2rem (32px);
border: 3px solid #E5E5E5;
border-top-color: #0070D2;
border-radius: 50%;
animation: spin 0.8s linear infinite;

/* Sizes */
/* X-Small: 1rem (16px) */
/* Small: 1.5rem (24px) */
/* Medium: 2rem (32px) */
/* Large: 2.75rem (44px) */

/* Brand spinner: border-top-color: #0070D2 */
/* Inverse spinner: on dark bg, border: rgba(255,255,255,0.35), top: #FFFFFF */
```

### Progress Bar
```css
/* Track */
height: 0.5rem (8px);
background: #E5E5E5;
border-radius: 15rem;

/* Fill */
background: #0070D2;
border-radius: 15rem;
height: 100%;
transition: width 0.3s ease;

/* Descriptive (with label) */
/* Label: 13px, color #706E6B, margin-bottom 0.25rem */
/* Value: 13px, color #080707, text-align right */

/* Success state: fill background: #2E844A */
```

### Accordion
```css
/* Section */
border-top: 1px solid #E5E5E5;

/* Section Header */
padding: 0.75rem 1rem;
font-size: 14px;
font-weight: 700;
color: #080707;
cursor: pointer;
display: flex;
align-items: center;

/* Toggle Icon */
/* Chevron right (collapsed) / chevron down (expanded) */
margin-right: 0.5rem;
width: 16px;
height: 16px;
transition: transform 0.2s ease;

/* Section Content */
padding: 0.5rem 1rem 1rem 1rem;
font-size: 13px;
color: #080707;

/* Hover */
background: #F3F3F3;

/* Focus */
box-shadow: 0 0 3px #0070D2 inset;
```

### Avatar
```css
/* Avatar */
border-radius: 50%;
overflow: hidden;
display: inline-flex;
align-items: center;
justify-content: center;
background: #706E6B;
color: #FFFFFF;
font-weight: 700;

/* Sizes */
/* X-Small: 1.25rem (20px), font 8px */
/* Small: 1.5rem (24px), font 10px */
/* Medium: 2rem (32px), font 13px */
/* Large: 3rem (48px), font 18px */
/* X-Large: 5rem (80px), font 28px */

/* Group Avatar */
/* Overlapping: margin-left: -0.5rem */
/* Border: 2px solid #FFFFFF */
```

### Breadcrumb
```css
/* Breadcrumb */
display: flex;
align-items: center;
gap: 0;
font-size: 12px;

/* Breadcrumb Item */
color: #0070D2;

/* Breadcrumb Separator */
color: #706E6B;
margin: 0 0.25rem;
/* "/" or chevron icon */

/* Current (last item) */
color: #080707;
font-weight: 400;
```

### Page Header
```css
/* Page Header */
background: #FFFFFF;
border-bottom: 1px solid #E5E5E5;
padding: 1rem 1.5rem;

/* Object Home */
/* Breadcrumb + Title + Actions layout */

/* Title */
font-size: 1.25rem (20px);
font-weight: 700;
color: #080707;
line-height: 1.25;

/* Meta / Subtitle */
font-size: 12px;
color: #706E6B;
margin-top: 0.125rem;

/* Actions */
display: flex;
gap: 0.5rem;
/* Aligned to the right */

/* Record Home (with icon) */
/* 2rem (32px) icon on left */
/* Title + meta stacked beside icon */
```

### Tree / Sidebar Navigation
```css
/* Tree Item */
padding: 0.5rem 1rem;
font-size: 13px;
color: #080707;
cursor: pointer;
border-left: 3px solid transparent;

/* Tree Item Hover */
background: #F3F3F3;

/* Tree Item Selected */
background: #EEF4FF;
border-left-color: #0070D2;
color: #0070D2;

/* Tree Item Expand/Collapse */
/* Chevron icon: 16px, margin-right 0.5rem */
/* Nested items: padding-left increases by 1rem per level */

/* Branch */
padding-left: 2rem; /* 1st level indent */
```

---

## Dark Mode (Inverse Theme)

SLDS uses "inverse" rather than a full dark mode. Key inverse tokens:

| Property | Light | Inverse |
|----------|-------|---------|
| Body bg | `#F3F3F3` | `#16325C` |
| Surface bg | `#FFFFFF` | `#1A1B1E` |
| Text | `#080707` | `#FFFFFF` |
| Text secondary | `#706E6B` | `#AEAEAE` |
| Primary | `#0070D2` | `#1B96FF` |
| Border | `#E5E5E5` | `#3A3A3C` |
| Input bg | `#FFFFFF` | `#3A3A3C` |
| Input border | `#706E6B` | `#5A5A5C` |
| Card bg | `#FFFFFF` | `#1A1B1E` |
| Link | `#0070D2` | `#1B96FF` |
| Hover bg | `#F3F3F3` | `#2A2A2C` |
| Shadow color | `rgba(0,0,0,0.10)` | `rgba(0,0,0,0.40)` |

### Inverse Implementation
```html
<!-- Apply inverse theme -->
<div class="slds-theme_inverse">...</div>
<div class="slds-theme_alt-inverse">...</div>
```

---

## Iconography

### Icon Categories
- **Utility Icons** — 16-20px, UI actions (close, search, settings)
- **Standard Icons** — 32-48px, object types (account, contact, lead) with colored backgrounds
- **Custom Icons** — 32-48px, custom object types
- **Action Icons** — 32-48px, circular background, specific actions
- **Doctype Icons** — File type indicators

### Standard Icon Background Colors
| Object | Background Color |
|--------|-----------------|
| Account | `#7F8DE1` |
| Contact | `#A094ED` |
| Lead | `#F88962` |
| Opportunity | `#FCB95B` |
| Case | `#F2CF5B` |
| Campaign | `#F49756` |
| Task | `#4BC076` |
| Event | `#EB7092` |
| Report | `#2ECBBE` |
| Dashboard | `#EF6E64` |
| Custom | `#A094ED` |

### Icon Sizing
| Size | Dimensions | Usage |
|------|-----------|-------|
| XX-Small | 14px | Inline with small text |
| X-Small | 16px | Utility in compact layouts |
| Small | 24px | Standard utility |
| Medium | 32px | Standard icons in lists |
| Large | 48px | Page headers, hero areas |
| X-Large | 60px | Landing pages |

---

## Data Visualization Colors

### Categorical Palette (in order)
```
#1589EE — Blue (primary)
#44CAF0 — Cyan
#3BA755 — Green
#F4BC25 — Yellow
#E57F25 — Orange
#C23934 — Red
#A094ED — Purple
#EB7092 — Pink
#16325C — Navy
#7F8DE1 — Lavender
```

### Sequential Palette
Blue: `#EEF4FF` -> `#D8EDFF` -> `#1B96FF` -> `#0070D2` -> `#014486`
Green: `#E6F7E9` -> `#45C65A` -> `#2E844A` -> `#194E31`

### Diverging Palette
Red-Blue: `#C23934` -> `#E57F25` -> `#F4BC25` -> `#FFFFFF` -> `#1B96FF` -> `#0070D2` -> `#014486`

### Chart Styling Rules
- Chart background: transparent
- Gridlines: `#E5E5E5`, horizontal preferred
- Axis labels: `#706E6B`, 12px
- Data labels: `#080707`, 12px, bold for emphasis
- Chart titles: `#080707`, 14px, bold
- Use `tabular-nums` on all numeric axis labels and data labels

---

## Layout Patterns

### App Structure
```
┌──────────────────────────────────────────┐
│ Global Header (50px)                     │
│ ■ App Launcher | Logo | Search | User    │
├──────────────────────────────────────────┤
│ Navigation Bar (40px)                    │
│ Tab1 | Tab2 | Tab3 (active) | Tab4       │
├──────────────────────────────────────────┤
│                                          │
│  Page Content (scrollable)               │
│  ┌────────────────────────────────────┐  │
│  │ Page Header                        │  │
│  │ Title + Actions                    │  │
│  ├────────────────────────────────────┤  │
│  │ Content Area                       │  │
│  │                                    │  │
│  └────────────────────────────────────┘  │
│                                          │
└──────────────────────────────────────────┘
```

### App Dimensions
| Element | Value |
|---------|-------|
| Global Header height | `50px` (3.125rem) |
| Global Header brand stripe | `3px solid #0070D2` (bottom) |
| Navigation bar height | `40px` (2.5rem) |
| Side panel width (narrow) | `240px` (15rem) |
| Side panel width (wide) | `320px` (20rem) |
| Utility bar height | `44px` |
| Footer height | `2.75rem` (44px) |

### Grid System
SLDS uses a 12-column fluid grid:

| Breakpoint | Width | Columns | Gutter |
|------------|-------|---------|--------|
| Small | >= 480px | 4-12 | 12px |
| Medium | >= 768px | 6-12 | 12px |
| Large | >= 1024px | 12 | 12px |
| X-Large | >= 1280px | 12 | 12px |

```css
/* Grid container */
display: flex;
flex-wrap: wrap;
margin: 0 -0.75rem; /* negative gutter */

/* Grid column */
padding: 0 0.75rem; /* gutter */
/* slds-size_1-of-12 through slds-size_12-of-12 */

/* Column sizing */
.slds-size_1-of-2 { width: 50%; }
.slds-size_1-of-3 { width: 33.3333%; }
.slds-size_1-of-4 { width: 25%; }
.slds-size_2-of-3 { width: 66.6667%; }
.slds-size_3-of-4 { width: 75%; }
```

### Content Area
- Container max-width: typically fluid within the app shell
- Container padding: 1rem (16px) horizontally
- Section spacing: 1rem (16px) between major sections
- Card grid gaps: 12px-16px

---

## Interaction States

All interactive elements follow this state pattern:

| State | Behavior |
|-------|----------|
| Default | Base styling |
| Hover | Background shifts to `#F3F3F3` or lighter brand |
| Active/Pressed | Darker variant (brand-darker `#014486`) |
| Focus | `box-shadow: 0 0 3px #0070D2; outline: 0;` |
| Disabled | Gray border `#C9C9C9`, gray text `#C9C9C9`, `cursor: not-allowed` |
| Selected | Blue highlight bg `#EEF4FF`, brand border accent |
| Error | Red border `#C23934`, red shadow, light red bg `#FEF1F1` |

### Focus Management
```css
/* Standard focus */
box-shadow: 0 0 3px #0070D2;
outline: 0;

/* Enhanced focus (for accessibility) */
box-shadow: 0 0 0 2px #FFFFFF, 0 0 0 4px #0070D2;
outline: 0;
```

### Transitions
```css
transition: border 0.15s linear, background-color 0.15s linear;
/* Or for all properties: */
transition: all 0.1s linear;
```

### Animation Tokens
| Token | Value | Usage |
|-------|-------|-------|
| `DURATION_INSTANTLY` | 0s | No animation |
| `DURATION_IMMEDIATELY` | 0.05s | Micro-interactions |
| `DURATION_QUICKLY` | 0.1s | Hover states |
| `DURATION_PROMPTLY` | 0.2s | Transitions |
| `DURATION_SLOWLY` | 0.4s | Complex animations |
| `DURATION_PAUSED` | 3.2s | Auto-dismiss toasts |

---

## CSS Class Naming Convention

SLDS uses BEM-inspired naming with the `slds-` prefix:

```
slds-[block]
slds-[block]__[element]
slds-[block]_[modifier]
```

### Common Classes
```css
/* Layout */
.slds-grid          /* flex container */
.slds-col           /* flex column */
.slds-wrap          /* flex-wrap: wrap */
.slds-align-center  /* align-items: center */
.slds-p-around_medium  /* padding: 1rem */
.slds-m-bottom_small   /* margin-bottom: 0.75rem */

/* Sizing */
.slds-size_1-of-2   /* width: 50% */
.slds-size_full     /* width: 100% */

/* Text */
.slds-text-heading_large  /* 20px heading */
.slds-text-body_regular   /* 13px body */
.slds-text-color_weak     /* #706E6B text */

/* Utilities */
.slds-truncate      /* text-overflow: ellipsis */
.slds-hide          /* display: none */
.slds-show          /* display: block */
.slds-is-relative   /* position: relative */
```

---

## Utility Classes

### Spacing
```css
/* Pattern: slds-[property]_[side]_[size] */
/* property: p (padding), m (margin) */
/* side: top, bottom, left, right, horizontal, vertical, around */
/* size: none, xxx-small, xx-small, x-small, small, medium, large, x-large, xx-large */

.slds-p-around_medium    /* padding: 1rem */
.slds-p-horizontal_small /* padding-left: 0.75rem; padding-right: 0.75rem */
.slds-m-top_x-small      /* margin-top: 0.5rem */
.slds-m-bottom_none      /* margin-bottom: 0 */
```

### Text Alignment
```css
.slds-text-align_center
.slds-text-align_right
.slds-text-align_left
```

### Visibility
```css
.slds-hide           /* display: none */
.slds-show           /* display: block */
.slds-show_inline    /* display: inline */
.slds-hidden         /* visibility: hidden */
.slds-visible        /* visibility: visible */
.slds-assistive-text /* sr-only equivalent */
```

### Truncation
```css
.slds-truncate {
  max-width: 100%;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
```

---

## Accessibility

### Focus Requirements
- All interactive elements must have visible focus indicators
- Focus ring: `box-shadow: 0 0 3px #0070D2`
- Enhanced: `box-shadow: 0 0 0 2px #FFFFFF, 0 0 0 4px #0070D2`
- Skip navigation link provided in Global Header
- Keyboard trap management for modals

### Color Contrast
- Normal text (#080707 on #FFFFFF): 19.29:1 (passes AAA)
- Brand text (#0070D2 on #FFFFFF): 4.65:1 (passes AA)
- Secondary text (#706E6B on #FFFFFF): 4.70:1 (passes AA)
- Error text (#C23934 on #FFFFFF): 4.62:1 (passes AA)
- White on brand (#FFFFFF on #0070D2): 4.65:1 (passes AA)

### ARIA Patterns
- Combobox: `role="combobox"` + `aria-expanded` + `aria-controls`
- Tabs: `role="tablist"` + `role="tab"` + `role="tabpanel"`
- Modal: `role="dialog"` + `aria-modal="true"` + `aria-labelledby`
- Alert: `role="alert"` or `role="status"` for live regions
- Tree: `role="tree"` + `role="treeitem"` + `aria-expanded`

---

## Quick Implementation Checklist

When building in SLDS style:

- [ ] Font: Salesforce Sans or Arial fallback
- [ ] Body text: 13px (platform) or 14px (standalone)
- [ ] Primary blue: `#0070D2`
- [ ] Page background: `#F3F3F3`
- [ ] Card background: `#FFFFFF`
- [ ] Border radius: `4px` on most components, `8px` on modals
- [ ] Shadows: directional (Y-offset), subtle (`rgba(0,0,0,0.10)`)
- [ ] Buttons: 32px height default, normal weight, 4px radius
- [ ] Global header: 50px, white bg, 3px blue bottom border
- [ ] Navigation: 40px tab bar
- [ ] Tables: uppercase 12px header text, `#FAFAF9` header bg
- [ ] Disabled: `#C9C9C9` border and text, `cursor: not-allowed`
- [ ] Focus: `box-shadow: 0 0 3px #0070D2`, no outline
- [ ] Transitions: `0.15s linear` (not ease-in-out)
- [ ] Inputs: `#706E6B` border, `#0070D2` on focus
- [ ] Labels: 12px, `#3E3E3C`
- [ ] Error states: `#C23934` border, `#FEF1F1` background
- [ ] Alerts: 4px left border accent
- [ ] Spacing: use 4px base (4, 8, 12, 16, 24, 32, 48)
- [ ] `slds-` prefix on all class names
- [ ] `tabular-nums` on all numeric displays

---

## SLDS vs. Tailwind Mapping

For teams familiar with Tailwind, here's how SLDS tokens map:

| SLDS | Nearest Tailwind | Note |
|------|-----------------|------|
| Gray 1 #F3F3F3 | `gray-100` | Warmer than Tailwind |
| Gray 2 #E5E5E5 | `gray-200` | SLDS grays are warm/neutral |
| Gray 5 #B0B0B0 | `gray-400` | |
| Gray 7 #706E6B | `gray-500` | Key secondary text color |
| Gray 9 #3E3E3C | `gray-700` | Label color |
| Text #080707 | `gray-900` | Near-black default text |
| Brand #0070D2 | `blue-600` | Slightly darker |
| Brand Dark #005FB2 | `blue-700` | |
| Error #C23934 | `red-600` | Warmer red |
| Success #2E844A | `green-600` | |
| Warning #DD7A01 | `amber-600` | More orange |
| Body 13px | `text-xs`/`text-sm` | Between Tailwind sizes |
| Radius 4px | `rounded` | Not `rounded-lg` |
| Shadow | `shadow-sm` | Directional, subtle |
| Page bg #F3F3F3 | `bg-gray-100` | |

**Critical differences from Tailwind defaults:**
1. Body text is 13px (not 14px or 16px) in the platform
2. Border radius is 4px (Tailwind's `rounded-lg` 8px is too large for most components)
3. Shadows are very subtle with low opacity (0.10)
4. Grays are warm/neutral (not cool blue-toned like Tailwind)
5. The page background is light gray (#F3F3F3), not white
6. Cards are white on gray background (opposite of many modern designs)
7. Global header has a 3px brand-blue bottom border accent
8. Table headers are uppercase with letter-spacing
9. Disabled state uses gray color (not opacity reduction)
10. Focus ring is a glow (`box-shadow: 0 0 3px`) not a ring (`0 0 0 Npx`)
