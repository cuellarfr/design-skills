# Visual Design Principles for Critique

How to evaluate the visual quality of a design using objective principles rather than personal taste.

---

## Visual Hierarchy

The most important design principle. It determines what users see first, second, and third.

### How to Check Visual Hierarchy

**The squint test:** Squint at the design (or blur it in Figma/Photoshop). What stands out? That should be the most important element. If the most important element doesn't stand out, hierarchy is broken.

**The 5-second test:** Show the design for 5 seconds. Ask: "What's this page about? What should you do here?" If the answer is wrong, hierarchy is broken.

### Tools for Creating Hierarchy

| Tool | How It Creates Hierarchy | Example |
|---|---|---|
| **Size** | Larger = more important | H1 > H2 > body text |
| **Weight** | Bolder = more important | Bold title vs. regular body |
| **Color** | Higher contrast = more important | Dark text on light bg vs. gray on light bg |
| **Position** | Top-left gets seen first (F-pattern reading) | Primary CTA above the fold |
| **Space** | More whitespace = more importance | Hero section with ample padding |
| **Density** | Less dense = more prominent | Single card vs. packed grid |

### Common Hierarchy Failures

| Problem | Visual Symptom | Fix |
|---|---|---|
| **No focal point** | Everything same size, weight, color | Make one element dramatically larger/bolder |
| **Too many focal points** | Multiple elements competing for attention | Choose one primary, reduce others |
| **Primary CTA isn't dominant** | Secondary buttons same visual weight as primary | Primary: filled, bold. Secondary: outlined or text-only |
| **Content hierarchy contradicts importance** | Decorative element is more prominent than the task | Reduce decorative elements; increase task prominence |

---

## Typography

### What to Check

| Aspect | Good Practice | Red Flag |
|---|---|---|
| **Type scale** | Clear, consistent size steps (e.g., 12, 14, 16, 20, 24, 32) | Random sizes; tiny differences (14 vs 15) |
| **Line length** | 45-75 characters per line (ideal ~66) | Full-width paragraphs on wide screens |
| **Line height** | 1.4-1.6× for body text; 1.1-1.3× for headings | Cramped text (1.0) or too airy (2.0+) |
| **Font pairings** | 2 typefaces max (1 serif + 1 sans, or 2 weights of same) | 3+ typefaces; fonts that clash |
| **Weight range** | Regular + Bold for body; use weight to create hierarchy | Thin weights for body text; all bold |
| **Readability** | ≥16px for body text; high contrast; adequate spacing | 12px body text; low contrast; tight spacing |
| **Alignment** | Consistent left-alignment for body; centered only for headings or short text | Centered paragraphs; mixed alignment without reason |

### Typography Hierarchy Formula

A workable type scale for most interfaces:

| Role | Size | Weight | Use |
|---|---|---|---|
| Page title / H1 | 28-36px | Bold (600-700) | One per page |
| Section title / H2 | 22-28px | Semibold (600) | Section dividers |
| Subsection / H3 | 18-22px | Medium (500) | Within sections |
| Body | 16px | Regular (400) | Main content |
| Secondary / Caption | 13-14px | Regular (400) | Supplementary info |
| Label / Overline | 11-12px | Medium (500), uppercase | Categories, metadata |

---

## Color

### What to Check

| Aspect | Good Practice | Red Flag |
|---|---|---|
| **Palette size** | 1 primary, 1-2 secondary, 1 accent + neutrals | 6+ distinct colors competing |
| **Semantic color** | Red = error, green = success, yellow = warning, blue = info | Red used for non-error; green for non-success |
| **Contrast** | Text ≥ 4.5:1 (AA); UI components ≥ 3:1 | Light text on light bg; low-contrast buttons |
| **Color as information** | Color + icon/text/pattern | Color is the only differentiator |
| **Consistency** | Same color = same meaning throughout | Blue means "link" in one place, "info" in another |
| **Saturation balance** | Most colors muted; accent saturated for emphasis | Everything saturated (visual noise) |

### Color Hierarchy

| Level | Color Treatment | Example |
|---|---|---|
| **Primary action** | Highest contrast, brand color, filled | "Save" button |
| **Secondary action** | Lower contrast, outlined or muted fill | "Cancel" button |
| **Tertiary action** | Text-only, minimal visual weight | "Learn more" link |
| **Destructive action** | Red/danger color, but still lower prominence than primary | "Delete" (unless it's the primary action) |
| **Disabled** | Gray, low opacity, no hover state | Unavailable option |

---

## Spacing and Layout

### What to Check

| Aspect | Good Practice | Red Flag |
|---|---|---|
| **Spacing scale** | Consistent multiples (4px or 8px base) | Random spacing; 13px here, 17px there |
| **Padding consistency** | Same padding inside same component type | Card with 16px padding on one page, 24px on another |
| **Proximity grouping** | Space between groups > space within groups | Even spacing everywhere (no grouping) |
| **Alignment** | Elements align to grid lines; left edges match | Slightly off-center elements; misaligned columns |
| **Responsive behavior** | Layout adapts gracefully; content reflows | Fixed widths; horizontal scroll; content overlap |
| **Density** | Appropriate for context (data-heavy = denser; marketing = spacious) | Dense dashboard for casual users; spacious table for power users |

### The 8px Grid

Most design systems use an 8px base unit:
- **4px** — Tight spacing (within components: icon to label)
- **8px** — Default spacing (between related elements)
- **16px** — Section spacing (between groups)
- **24px** — Large spacing (between sections)
- **32-48px** — Extra-large (page margins, hero padding)

### Whitespace as Design Tool

Whitespace isn't empty — it's functional:
- **Micro whitespace** (2-8px): Between letters, within components
- **Macro whitespace** (16-48px): Between sections, around focal elements

**More whitespace around an element = more perceived importance.**

---

## Consistency

### Three Levels of Consistency

| Level | What to Check | Impact |
|---|---|---|
| **Visual** | Same colors, fonts, spacing, border-radius | Product feels cohesive vs. patchwork |
| **Behavioral** | Same interaction = same response | Users build reliable mental models |
| **Verbal** | Same action = same label | "Delete" vs. "Remove" vs. "Trash" confusion |

### Consistency Audit Checklist

**Buttons:**
- [ ] Primary/secondary/tertiary have distinct, consistent styles
- [ ] Same label for same action throughout
- [ ] Same size in same context
- [ ] Consistent border-radius

**Forms:**
- [ ] Label position consistent (all above, or all beside)
- [ ] Input height consistent
- [ ] Error style consistent
- [ ] Required field indicator consistent

**Cards/Containers:**
- [ ] Same padding, border-radius, shadow
- [ ] Same image aspect ratio
- [ ] Same content order (title, description, metadata)

**Icons:**
- [ ] Same style (all outlined or all filled, same weight)
- [ ] Same size in same context
- [ ] Same meaning — gear always means settings

**Navigation:**
- [ ] Same placement on every page
- [ ] Active state consistent
- [ ] Same items in same order

---

## State Design

Every interactive element exists in multiple states. Missing states create confusion.

### States to Design For

| State | When | Visual Treatment |
|---|---|---|
| **Default** | Element at rest | Standard appearance |
| **Hover** | Cursor over element | Subtle highlight (darken 5-10%, underline for links) |
| **Focus** | Keyboard navigation | Clear outline (2px+ solid, high contrast) |
| **Active/Pressed** | Being clicked/tapped | Brief darken or scale-down |
| **Selected** | Currently chosen item | Distinct from hover — persistent highlight |
| **Disabled** | Not available | Reduced opacity (40-50%), no pointer cursor, no hover |
| **Loading** | Waiting for response | Spinner, skeleton, or shimmer |
| **Error** | Validation failed | Red border + error text |
| **Success** | Action completed | Green highlight + confirmation text |
| **Empty** | No content yet | Illustration + guidance + CTA |

### Common State Failures

| Failure | User Impact | Fix |
|---|---|---|
| No hover state | User unsure if element is interactive | Add subtle hover change |
| Hover but no focus | Keyboard users can't see where they are | Always pair hover and focus styles |
| Disabled looks like default | User thinks they can click; nothing happens | Reduce opacity significantly; change cursor |
| No loading state | User thinks click didn't register; clicks again | Show spinner or skeleton immediately |
| No empty state | User sees blank screen; thinks it's broken | Add helpful empty state with guidance |
| No error state | User submits and nothing happens | Show inline error with explanation |
