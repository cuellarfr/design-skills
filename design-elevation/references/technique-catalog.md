# Design Technique Catalog

Specific visual moves organized by what they achieve. Each technique includes implementation details and when to apply.

## Techniques for Visual Hierarchy

### The Typographic Waterfall
**What it achieves**: Clear content hierarchy without heavy styling
**Implementation**:
- Start with 64px for primary headlines
- Step down by 0.75x for each level (64 → 48 → 36 → 27 → 20)
- Combine with weight changes (700 → 600 → 500 → 400)
- Use tighter line-height as size increases (1.1 for display, 1.6 for body)
**When to use**: Document headers, presentation titles, report sections

### The Swiss Grid System
**What it achieves**: Invisible structure that creates order
**Implementation**:
- Use 12-column or 16-column base grid
- Create margins equal to 2-3 column widths
- Align all elements to grid lines
- Use gutters of 20-32px depending on scale
**When to use**: Dashboards, complex layouts, multi-panel interfaces

### The Fibonacci Spacing
**What it achieves**: Natural, pleasing proportions
**Implementation**:
- Base unit: 8px
- Scale: 8, 13, 21, 34, 55, 89, 144px
- Apply to margins, padding, gaps
- Use larger values for major sections
**When to use**: When default spacing feels mechanical

## Techniques for Sophistication

### The Near-Black Treatment
**What it achieves**: Softer, more sophisticated than pure black
**Implementation**:
- Text: #1a1a1a to #2d2d2d (not #000000)
- Backgrounds: #0a0a0a to #121212
- Add slight color tint: rgb(26, 27, 30) for cool, rgb(30, 27, 26) for warm
**When to use**: Any dark text or backgrounds

### The Colored Shadow Technique
**What it achieves**: Natural, integrated depth
**Implementation**:
```css
box-shadow: 
  0 2px 4px rgba(31, 35, 53, 0.06),
  0 4px 8px rgba(31, 35, 53, 0.08);
```
- Use color from the element, darkened
- Multiple layers for realism
- Avoid pure black shadows
**When to use**: Cards, modals, elevated elements

### The Gradient Mesh Background
**What it achieves**: Subtle, modern depth
**Implementation**:
```css
background: 
  radial-gradient(at 40% 20%, hsla(280, 100%, 96%, 1) 0px, transparent 50%),
  radial-gradient(at 80% 0%, hsla(340, 100%, 95%, 0.8) 0px, transparent 50%),
  radial-gradient(at 0% 50%, hsla(220, 100%, 97%, 0.9) 0px, transparent 50%);
```
**When to use**: Hero sections, slide backgrounds, empty states

## Techniques for Premium Feel

### The Optical Scaling
**What it achieves**: Perfect visual balance at any size
**Implementation**:
- Headlines > 48px: -0.02em letter-spacing
- Headlines 32-48px: -0.01em letter-spacing  
- Body text: 0 letter-spacing
- Small text < 14px: +0.01em letter-spacing
- Adjust line height inversely with size
**When to use**: Any text, especially headings

### The Micro-Animation
**What it achieves**: Subtle life without distraction
**Implementation**:
```css
transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
/* Hover states */
transform: translateY(-2px);
box-shadow: 0 4px 12px rgba(0,0,0,0.08);
```
**When to use**: Interactive elements, hover states

### The Ink Trap Detail
**What it achieves**: Subtle sophistication in corners
**Implementation**:
- Cut 2-4px triangles from rectangle corners
- Or use gradient masks for rounded ink traps
- Apply to cards, buttons, containers
**When to use**: When standard rectangles feel too simple

## Techniques for Data Visualization

### The Muted Palette Approach
**What it achieves**: Sophisticated, non-overwhelming charts
**Implementation**:
- Primary: hsla(220, 70%, 50%, 1)
- Variants: Adjust lightness ±15% for series
- Grays: hsla(220, 10%, 40-80%, 1)
- Avoid pure/saturated colors
**When to use**: Any data visualization

### The Thin Line Method
**What it achieves**: Elegant, modern charts
**Implementation**:
- Line thickness: 1.5-2px maximum
- Grid lines: 0.5px at 20% opacity
- Remove all borders from chart area
- Use dots (4-6px) for data points
**When to use**: Line charts, area charts

### The Annotation Layer
**What it achieves**: Context without clutter
**Implementation**:
- Annotations in gray, 2 sizes smaller than data
- Leader lines at 0.5px, 30% opacity
- Position outside plot area when possible
- Use consistent annotation style
**When to use**: Complex charts needing explanation

## Techniques for Typography

### The Type Scale Lock
**What it achieves**: Perfect proportions across breakpoints
**Implementation**:
```css
font-size: clamp(1rem, 0.9rem + 0.5vw, 1.25rem);
font-size: clamp(2rem, 1.5rem + 2.5vw, 4rem);
```
**When to use**: Responsive designs, fluid layouts

### The Hanging Punctuation
**What it achieves**: Optically aligned text blocks
**Implementation**:
```css
.quote::before {
  content: '"';
  margin-left: -0.4em;
}
```
**When to use**: Pull quotes, testimonials, body text

### The Variable Font Finesse
**What it achieves**: Precise typographic control
**Implementation**:
- Use weight 380-420 for body (not 400)
- Increase weight slightly for white-on-dark
- Adjust width for different viewport sizes
- Fine-tune optical size axis
**When to use**: When variable fonts available

## Techniques for Color

### The Triadic Harmony
**What it achieves**: Vibrant but balanced palettes
**Implementation**:
- Choose base hue
- Add colors at +120° and +240°
- Adjust saturation/lightness for balance
- Use 60-30-10 distribution
**When to use**: When needing multiple accent colors

### The Monochromatic Depth
**What it achieves**: Sophisticated, cohesive feeling
**Implementation**:
- Base hue: e.g., 220°
- Create 7-9 variants adjusting only S and L
- Range: 5% to 95% lightness
- Slight saturation variations (40-70%)
**When to use**: Professional documents, reports

### The Vibrating Edge
**What it achieves**: Energy at color boundaries
**Implementation**:
- Place complementary colors adjacent
- Match value (lightness) closely
- Use for small accents only
- Example: red-green, blue-orange edges
**When to use**: Sparingly, for emphasis points

## Techniques for Layout

### The Breaking Grid
**What it achieves**: Dynamic tension
**Implementation**:
- Establish strict grid
- Break 1-2 elements deliberately
- Overlap, extend, or rotate
- Maintain alignment on one edge
**When to use**: When layouts feel too rigid

### The Diagonal Balance
**What it achieves**: Dynamic composition
**Implementation**:
- Place heavy elements on diagonal
- Balance with negative space
- Use 30°, 45°, or 60° angles
- Maintain some horizontal/vertical elements
**When to use**: Hero sections, feature highlights

### The Modular Component System
**What it achieves**: Consistency with flexibility
**Implementation**:
- Create 3-5 base component sizes
- Use consistent padding ratios
- Apply same corner radius logic
- Build layouts from combinations
**When to use**: Dashboards, card layouts

## Techniques for Polish

### The Subtle Texture
**What it achieves**: Depth without distraction
**Implementation**:
```css
background-image: 
  repeating-linear-gradient(
    45deg,
    transparent,
    transparent 35px,
    rgba(255,255,255,.01) 35px,
    rgba(255,255,255,.01) 70px
  );
```
**When to use**: Large background areas

### The Perfect Corners
**What it achieves**: Consistent, intentional rounding
**Implementation**:
- Use one system: 0, 4, 8, 16, 24px
- Or proportional: 0.25rem, 0.5rem, 1rem
- Match nested elements (outer - padding = inner)
- Consider "squircle" for iOS-like smoothness
**When to use**: All rounded elements

### The Loading Sophistication
**What it achieves**: Premium feel during waits
**Implementation**:
- Skeleton screens over spinners
- Smooth gradient animations
- Staggered element appearances
- Easing: cubic-bezier(0.4, 0, 0.2, 1)
**When to use**: Any loading state

## Quick Application Guide

### For "Make it feel expensive"
- Apply Near-Black Treatment
- Use Optical Scaling
- Add Colored Shadows
- Implement Perfect Corners

### For "Make it more modern"  
- Use Gradient Mesh Backgrounds
- Apply Thin Line Method
- Add Micro-Animations
- Break the Grid deliberately

### For "Make it cleaner"
- Implement Swiss Grid System
- Use Monochromatic Depth
- Apply Fibonacci Spacing
- Add white space generously

### For "Make it pop"
- Use Vibrating Edge (sparingly)
- Apply Diagonal Balance
- Increase type scale contrast
- Add one bold color accent