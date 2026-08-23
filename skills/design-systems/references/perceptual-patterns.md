# Perceptual Patterns

The aesthetic and experiential properties that make a product feel like itself. Perceptual patterns express brand personality through color, typography, spacing, motion, and voice.

---

## Color Systems

### Building a Color Palette

A complete color system has four layers:

**1. Brand colors (1-3)**
The signature colors that define the brand. Typically a primary and 1-2 secondary accent colors.

**2. Neutral palette (7-11 shades)**
The workhorse palette for backgrounds, text, borders, and surfaces. Build from a base gray:

| Token | Lightness | Usage |
|-------|-----------|-------|
| `gray-50` | 97% | Page background, subtle fills |
| `gray-100` | 93% | Card backgrounds, hover states |
| `gray-200` | 87% | Borders, dividers |
| `gray-300` | 80% | Disabled text, placeholder |
| `gray-400` | 65% | Secondary icons |
| `gray-500` | 50% | Secondary text |
| `gray-600` | 40% | Body text (on light backgrounds) |
| `gray-700` | 30% | Headings |
| `gray-800` | 20% | High-emphasis text |
| `gray-900` | 10% | Maximum contrast text |

**3. Semantic colors (4-6)**

| Role | Default Color Range | Mandatory |
|------|-------------------|-----------|
| `error` | Red | Yes |
| `success` | Green | Yes |
| `warning` | Yellow/Amber | Yes |
| `info` | Blue | Yes |
| `accent` | Brand-derived | Optional |
| `highlight` | Yellow or brand | Optional |

Each semantic color needs: base, light (backgrounds), dark (text), and border variants.

**4. Extended palette (per-color ramps)**
10-shade ramps (50-900) for each brand and semantic color. Generate mathematically — don't eyeball intermediate shades.

### Color Usage Rules

- **60-30-10 rule**: 60% neutral, 30% secondary, 10% accent — as a starting point, not a rigid law
- **One accent color per screen area**: Multiple competing accents create visual noise
- **Never use color as the only way to convey meaning** (WCAG 1.4.1): Always pair color with text, icons, or patterns
- **Contrast requirements**:
  - Body text: 4.5:1 minimum (AA), 7:1 (AAA)
  - Large text (>=18px or >=14px bold): 3:1 minimum (AA), 4.5:1 (AAA)
  - UI components and graphical objects: 3:1 minimum (AA)
  - Focus indicators: 3:1 against adjacent colors

---

## Typography Scales

### Mathematical Scales

Choose a ratio and base size. Every size in the system is derived from `base × ratio^n`:

| Scale Name | Ratio | Character | Best For |
|------------|-------|-----------|----------|
| Minor Second | 1.067 | Subtle | Dense UIs, data tables |
| Major Second | 1.125 | Gentle | Body-heavy content, documentation |
| Minor Third | 1.200 | Moderate | General-purpose, balanced hierarchy |
| Major Third | 1.250 | Pronounced | Marketing, editorial |
| Perfect Fourth | 1.333 | Strong | Landing pages, presentations |
| Golden Ratio | 1.618 | Dramatic | Expressive brands, hero sections |

### Practical Type Scale (base 16px, 1.25 ratio)

| Token | Size | Line Height | Weight | Usage |
|-------|------|-------------|--------|-------|
| `font-size-xs` | 12px | 1.5 (18px) | Regular | Captions, footnotes, legal |
| `font-size-sm` | 14px | 1.5 (21px) | Regular | Secondary text, labels, metadata |
| `font-size-md` | 16px | 1.5 (24px) | Regular | Body text — the default |
| `font-size-lg` | 20px | 1.4 (28px) | Medium | Lead paragraphs, card titles |
| `font-size-xl` | 25px | 1.3 (33px) | Semibold | Section headings (h3) |
| `font-size-2xl` | 31px | 1.25 (39px) | Semibold | Page sub-headings (h2) |
| `font-size-3xl` | 39px | 1.2 (47px) | Bold | Page headings (h1) |
| `font-size-4xl` | 49px | 1.1 (54px) | Bold | Display, hero titles |

### Typography Rules

1. **Maximum 2 font families**: One for headings, one for body — or a single family with sufficient weight range
2. **Minimum body size 16px on web, 14px on mobile**: Below this, readability drops sharply
3. **Line height decreases as size increases**: 1.5 for body → 1.1 for display — large text needs less leading
4. **Measure (line length)**: 45-75 characters for body text. 66 characters is optimal (Bringhurst)
5. **Weight range**: Use at minimum Regular (400), Medium (500), and Bold (700). Don't use more than 4 weights
6. **Letter spacing**: Slightly increase (+0.01-0.02em) for all-caps text. Slightly decrease (-0.01em) for display sizes (>36px)

---

## Spacing Systems

### Base Unit Approach

Choose a base unit and build all spacing from multipliers of it:

**Common base units:**
- **4px**: Fine-grained control. Good for dense UIs (dashboards, data apps)
- **8px**: Most common. Balances flexibility and simplicity
- **Hybrid 4/8px**: 4px for internal component spacing, 8px for layout spacing

### Spacing Scale (8px base)

| Token | Value | Usage |
|-------|-------|-------|
| `space-0` | 0px | Reset, collapsed states |
| `space-1` | 4px | Tight inline spacing (icon-to-label) |
| `space-2` | 8px | Default inline spacing, small gaps |
| `space-3` | 12px | Between related elements within a component |
| `space-4` | 16px | Default padding, between form fields |
| `space-6` | 24px | Between components within a section |
| `space-8` | 32px | Between sections |
| `space-12` | 48px | Between major page sections |
| `space-16` | 64px | Page margins, hero padding |
| `space-24` | 96px | Maximum section separation |

### Spacing Application Rules

**Two dimensions of spacing:**

| Type | Direction | Usage |
|------|-----------|-------|
| **Stack** | Vertical (top/bottom) | Between stacked elements: heading → paragraph → button |
| **Inline** | Horizontal (left/right) | Between side-by-side elements: icon → label, tag → tag |

**Gestalt principles in spacing:**
- **Proximity**: Related elements have less space between them than unrelated elements. A form label should be closer to its input (4-8px) than to the previous form field (16-24px)
- **Consistency**: All cards in a grid use the same gap. All section dividers use the same margin
- **Density intention**: More space = premium, editorial feel. Less space = efficient, data-dense feel

---

## Motion Principles

### Purpose of Motion

Motion in UI serves four functions:

| Function | When to Use | Duration Range |
|----------|------------|----------------|
| **Feedback** | Confirming a user action (button press, toggle) | 100-200ms |
| **Orientation** | Showing spatial relationships (page transitions, panels) | 200-400ms |
| **Focus** | Directing attention to something new (notifications, tooltips) | 150-300ms |
| **Delight** | Brand personality moments (success animations, loading) | 300-600ms |

### Duration Guidelines

| Interaction | Duration | Easing |
|------------|----------|--------|
| Hover state change | 100-150ms | ease-out |
| Button press | 100ms | ease-in-out |
| Tooltip appear | 150ms | ease-out |
| Modal open | 200-250ms | ease-out |
| Modal close | 150-200ms | ease-in |
| Page transition | 250-350ms | ease-in-out |
| Skeleton → content | 200ms | ease-out |
| Success animation | 400-600ms | spring/bounce |

### Motion Rules

1. **Faster = more responsive**: Feedback animations under 200ms. Never exceed 400ms for direct interactions
2. **Enter slower, exit faster**: Open a modal in 250ms, close it in 150ms — arrival is celebrated, departure is swift
3. **Match distance**: Larger movements take longer. A dropdown appearing directly below a button (short distance) is faster than a side panel sliding in from off-screen (long distance)
4. **Respect `prefers-reduced-motion`**: Always provide a reduced-motion alternative. Minimum: remove movement, keep opacity fades. Ideal: instant state changes with no animation
5. **Consistent easing**: Use a maximum of 3 easing curves system-wide — standard (ease-out), enter (ease-out), exit (ease-in)
6. **No gratuitous animation**: If removing an animation doesn't reduce usability or brand expression, remove it

### Motion Tokens

```
motion-duration-instant:  0ms
motion-duration-fast:     100ms
motion-duration-normal:   200ms
motion-duration-slow:     300ms
motion-duration-slower:   400ms
motion-easing-standard:   cubic-bezier(0.2, 0, 0, 1)
motion-easing-enter:      cubic-bezier(0, 0, 0.2, 1)
motion-easing-exit:       cubic-bezier(0.4, 0, 1, 1)
```

---

## Voice and Tone

### Voice (Constant)

Voice is the product's personality — it doesn't change. Define 3-4 voice attributes:

**Template:**
> We are **[attribute 1]** but not **[opposite extreme]**.
> We are **[attribute 2]** but not **[opposite extreme]**.
> We are **[attribute 3]** but not **[opposite extreme]**.

**Example:**
> We are **confident** but not arrogant.
> We are **helpful** but not patronizing.
> We are **clear** but not dumbed-down.
> We are **friendly** but not frivolous.

### Tone (Varies by Context)

Tone adapts to the situation while voice stays the same:

| Context | Tone Adjustment | Example |
|---------|----------------|---------|
| **Success** | Warm, encouraging | "You're all set! Your changes have been saved." |
| **Error** | Empathetic, direct | "We couldn't save your changes. Check your connection and try again." |
| **Onboarding** | Welcoming, guiding | "Let's set up your workspace. This takes about 2 minutes." |
| **Empty state** | Helpful, action-oriented | "No projects yet. Create your first project to get started." |
| **Destructive action** | Serious, clear | "This will permanently delete 23 files. This can't be undone." |
| **Loading/waiting** | Reassuring, brief | "Generating your report..." |

### Writing Rules for UI

1. **Lead with the action**: "Save changes" not "Do you want to save?"
2. **Use sentence case**: "Create new project" not "Create New Project" (title case is for marketing, not UI)
3. **Be specific**: "Delete 3 items" not "Delete items" — specificity builds trust
4. **No jargon**: "Something went wrong" not "Error 500: Internal server exception"
5. **No blame**: "We couldn't find that page" not "You entered an invalid URL"
6. **Active voice**: "We saved your draft" not "Your draft has been saved"

---

## Signature Moments

Signature moments are the distinctive, memorable interactions that express brand personality at key emotional points.

### Where to Place Them

- **First impression**: Onboarding, welcome screen, first successful action
- **Achievement**: Completing a workflow, reaching a milestone, shipping something
- **Recovery**: Coming back after an error, resuming after time away
- **Delight**: Unexpected pleasant touches during routine tasks

### Rules for Signature Moments

1. **Earn the moment**: Only at genuine emotional peaks — not on every button click
2. **Brief**: 300-600ms. Never block the user's flow
3. **Skippable**: Power users should be able to bypass them without friction
4. **Accessible**: Work without motion (static illustration + text), without sound (visual feedback), and without color
5. **Consistent**: The same moment should trigger the same expression every time — surprise is good, inconsistency isn't

### Examples from Real Products
- Slack's loading messages (warm, human)
- Mailchimp's high-five after sending a campaign (celebration)
- Linear's smooth, precise transitions (craftsmanship)
- Stripe's documentation animations (clarity through motion)
