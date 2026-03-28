# Spacing Systems & Visual Rhythm

Systematic approaches to spacing that create consistent, harmonious layouts.

## Base Spacing Systems

### Linear Scale (Arithmetic)
```css
/* Simple addition - predictable, stable */
:root {
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 20px;
  --space-6: 24px;
  --space-7: 28px;
  --space-8: 32px;
}
```

### Exponential Scale (Geometric)
```css
/* Multiplied by constant - dramatic, dynamic */
:root {
  --space-xs: 2px;     /* 2^1 */
  --space-sm: 4px;     /* 2^2 */
  --space-md: 8px;     /* 2^3 */
  --space-lg: 16px;    /* 2^4 */
  --space-xl: 32px;    /* 2^5 */
  --space-2xl: 64px;   /* 2^6 */
  --space-3xl: 128px;  /* 2^7 */
}
```

### T-Shirt Sizing
```css
/* Intuitive naming */
:root {
  --space-3xs: 2px;
  --space-2xs: 4px;
  --space-xs: 8px;
  --space-s: 12px;
  --space-m: 16px;
  --space-l: 24px;
  --space-xl: 32px;
  --space-2xl: 48px;
  --space-3xl: 64px;
  --space-4xl: 96px;
  --space-5xl: 128px;
}
```

## Advanced Spacing Systems

### Material Design Spacing
```css
/* 8dp grid system */
:root {
  --space-0: 0;
  --space-1: 8px;
  --space-2: 16px;
  --space-3: 24px;
  --space-4: 32px;
  --space-5: 40px;
  --space-6: 48px;
  --space-7: 56px;
  --space-8: 64px;
  --space-9: 72px;
}

/* Component spacing */
.material-card {
  padding: var(--space-2);
  margin: var(--space-1);
  border-radius: 4px;
}
```

### Tailwind Spacing
```css
/* 0.25rem increments */
:root {
  --space-0: 0;
  --space-px: 1px;
  --space-0.5: 0.125rem;  /* 2px */
  --space-1: 0.25rem;     /* 4px */
  --space-1.5: 0.375rem;  /* 6px */
  --space-2: 0.5rem;      /* 8px */
  --space-2.5: 0.625rem;  /* 10px */
  --space-3: 0.75rem;     /* 12px */
  --space-4: 1rem;        /* 16px */
  --space-5: 1.25rem;     /* 20px */
  --space-6: 1.5rem;      /* 24px */
  --space-8: 2rem;        /* 32px */
  --space-10: 2.5rem;     /* 40px */
  --space-12: 3rem;       /* 48px */
  --space-16: 4rem;       /* 64px */
  --space-20: 5rem;       /* 80px */
  --space-24: 6rem;       /* 96px */
}
```

## Component-Specific Spacing

### Button Spacing
```css
/* Optimal button padding */
.btn-small {
  padding: 6px 12px;
  font-size: 14px;
  line-height: 20px;
}

.btn-medium {
  padding: 8px 16px;
  font-size: 16px;
  line-height: 24px;
}

.btn-large {
  padding: 12px 24px;
  font-size: 18px;
  line-height: 28px;
}

/* Icon button spacing */
.btn-icon {
  padding: 8px;
  width: 40px;
  height: 40px;
}
```

### Card Spacing
```css
.card {
  padding: 24px;
  border-radius: 8px;
}

.card-compact {
  padding: 16px;
  border-radius: 6px;
}

.card-spacious {
  padding: 32px;
  border-radius: 12px;
}

/* Internal card spacing */
.card-header {
  margin-bottom: 16px;
  padding-bottom: 16px;
  border-bottom: 1px solid var(--border-light);
}

.card-body {
  margin-bottom: 20px;
}

.card-footer {
  margin-top: 20px;
  padding-top: 16px;
  border-top: 1px solid var(--border-light);
}
```

### Form Spacing
```css
.form-group {
  margin-bottom: 24px;
}

.form-label {
  margin-bottom: 8px;
  display: block;
}

.form-input {
  padding: 10px 12px;
  line-height: 20px;
}

.form-help-text {
  margin-top: 6px;
  font-size: 14px;
}

.form-error {
  margin-top: 4px;
  font-size: 14px;
}

/* Form sections */
.form-section {
  margin-bottom: 32px;
  padding-bottom: 32px;
  border-bottom: 1px solid var(--border-light);
}
```

## Layout Spacing Patterns

### Section Spacing
```css
/* Page sections */
.section {
  padding: 80px 0;
}

.section-small {
  padding: 40px 0;
}

.section-large {
  padding: 120px 0;
}

/* Hero sections */
.hero {
  padding: 160px 0;
}

.hero-compact {
  padding: 80px 0;
}

/* Content blocks */
.content-block + .content-block {
  margin-top: 48px;
}
```

### Stack Spacing
```css
/* Vertical stacks */
.stack-xs > * + * { margin-top: 4px; }
.stack-sm > * + * { margin-top: 8px; }
.stack-md > * + * { margin-top: 16px; }
.stack-lg > * + * { margin-top: 24px; }
.stack-xl > * + * { margin-top: 32px; }
.stack-2xl > * + * { margin-top: 48px; }

/* Responsive stacks */
.stack {
  display: flex;
  flex-direction: column;
  gap: var(--stack-gap, 16px);
}

@media (min-width: 768px) {
  .stack {
    --stack-gap: 24px;
  }
}

@media (min-width: 1024px) {
  .stack {
    --stack-gap: 32px;
  }
}
```

### Grid Gaps
```css
/* Standard grid gaps */
.gap-xs { gap: 4px; }
.gap-sm { gap: 8px; }
.gap-md { gap: 16px; }
.gap-lg { gap: 24px; }
.gap-xl { gap: 32px; }
.gap-2xl { gap: 48px; }

/* Asymmetric gaps */
.gap-x-md { column-gap: 16px; }
.gap-y-lg { row-gap: 24px; }

/* Responsive gaps */
.responsive-gap {
  gap: 16px;
}

@media (min-width: 768px) {
  .responsive-gap {
    gap: 24px;
  }
}

@media (min-width: 1024px) {
  .responsive-gap {
    gap: 32px;
  }
}
```

## Typography Spacing

### Line Height Relationships
```css
/* Optimal line height by font size */
.text-xs {
  font-size: 12px;
  line-height: 16px; /* 1.33x */
}

.text-sm {
  font-size: 14px;
  line-height: 20px; /* 1.43x */
}

.text-base {
  font-size: 16px;
  line-height: 24px; /* 1.5x */
}

.text-lg {
  font-size: 18px;
  line-height: 28px; /* 1.56x */
}

.text-xl {
  font-size: 20px;
  line-height: 30px; /* 1.5x */
}

.text-2xl {
  font-size: 24px;
  line-height: 32px; /* 1.33x */
}

.text-3xl {
  font-size: 30px;
  line-height: 36px; /* 1.2x */
}

.text-4xl {
  font-size: 36px;
  line-height: 40px; /* 1.11x */
}

.text-5xl {
  font-size: 48px;
  line-height: 52px; /* 1.08x */
}
```

### Paragraph Spacing
```css
/* Article typography */
.article {
  font-size: 18px;
  line-height: 1.7;
}

.article p {
  margin-bottom: 1.5em;
}

.article h2 {
  margin-top: 2.5em;
  margin-bottom: 0.75em;
}

.article h3 {
  margin-top: 2em;
  margin-bottom: 0.5em;
}

.article blockquote {
  margin: 2em 0;
  padding-left: 1.5em;
}

.article ul,
.article ol {
  margin: 1.5em 0;
  padding-left: 1.5em;
}

.article li + li {
  margin-top: 0.5em;
}
```

## White Space Principles

### Micro White Space
```css
/* Between letters and words */
.tight-tracking { letter-spacing: -0.05em; }
.normal-tracking { letter-spacing: 0; }
.loose-tracking { letter-spacing: 0.05em; }
.wide-tracking { letter-spacing: 0.1em; }

/* Word spacing */
.tight-words { word-spacing: -0.05em; }
.normal-words { word-spacing: normal; }
.loose-words { word-spacing: 0.1em; }
```

### Macro White Space
```css
/* Major sections */
.breathing-room {
  margin: 80px auto;
  padding: 60px;
}

.compact-layout {
  margin: 20px auto;
  padding: 20px;
}

.spacious-layout {
  margin: 120px auto;
  padding: 80px;
}
```

### Active vs Passive Space
```css
/* Active space - intentional emphasis */
.hero-space {
  min-height: 80vh;
  display: grid;
  place-items: center;
  padding: 120px 40px;
}

/* Passive space - separation */
.divider-space {
  height: 60px;
}

.section-break {
  margin: 60px 0;
}
```

## Responsive Spacing Strategies

### Fluid Spacing
```css
/* Viewport-based spacing */
.fluid-padding {
  padding: clamp(20px, 5vw, 80px);
}

.fluid-margin {
  margin: clamp(16px, 4vw, 64px) auto;
}

.fluid-gap {
  gap: clamp(16px, 2vw, 32px);
}
```

### Container Query Spacing
```css
@container (min-width: 400px) {
  .card {
    padding: 24px;
  }
}

@container (min-width: 600px) {
  .card {
    padding: 32px;
  }
}
```

### Aspect Ratio Spacing
```css
/* Maintain proportional spacing */
.square {
  aspect-ratio: 1 / 1;
  padding: 10%;
}

.golden {
  aspect-ratio: 1.618 / 1;
  padding: 5%;
}

.wide {
  aspect-ratio: 16 / 9;
  padding: 2.5%;
}
```

## Platform-Specific Spacing

### iOS/Apple Design
```css
:root {
  --ios-spacing-xs: 8px;
  --ios-spacing-sm: 12px;
  --ios-spacing-md: 16px;
  --ios-spacing-lg: 20px;
  --ios-spacing-xl: 32px;
  --ios-edge-margin: 20px;
  --ios-safe-area: env(safe-area-inset-top);
}
```

### Material Design
```css
:root {
  --material-baseline: 8px;
  --material-spacing-1: 8px;
  --material-spacing-2: 16px;
  --material-spacing-3: 24px;
  --material-keyline-1: 16px;
  --material-keyline-2: 72px;
}
```

### Microsoft Fluent
```css
:root {
  --fluent-spacing-xs: 4px;
  --fluent-spacing-s: 8px;
  --fluent-spacing-m: 12px;
  --fluent-spacing-l: 16px;
  --fluent-spacing-xl: 24px;
  --fluent-spacing-xxl: 32px;
}
```

## Spacing in Data Visualization

### Chart Spacing
```css
.chart-container {
  padding: 20px;
}

.chart-title {
  margin-bottom: 16px;
}

.chart-legend {
  margin-top: 20px;
  gap: 16px;
}

.axis-label {
  margin: 8px;
}

/* Bar chart spacing */
.bar-spacing {
  --bar-gap: 4px;
  --group-gap: 12px;
  --category-gap: 24px;
}
```

### Table Spacing
```css
.table {
  border-spacing: 0;
}

.table th,
.table td {
  padding: 12px 16px;
}

.table-compact th,
.table-compact td {
  padding: 8px 12px;
}

.table-spacious th,
.table-spacious td {
  padding: 16px 20px;
}

/* Row spacing */
.table-striped tr:nth-child(even) {
  background: rgba(0, 0, 0, 0.02);
}
```

## Spacing Debugging Tools

### Visual Spacing Guides
```css
/* Show all spacing */
* {
  outline: 1px solid rgba(255, 0, 0, 0.2);
}

/* Show margins */
*[class*="margin"] {
  background: rgba(255, 255, 0, 0.1);
}

/* Show padding */
*[class*="padding"] {
  background: rgba(0, 255, 0, 0.1);
}

/* Grid gaps visualization */
.show-gaps {
  gap: 16px;
  background: repeating-linear-gradient(
    90deg,
    transparent,
    transparent 16px,
    rgba(255, 0, 0, 0.1) 16px,
    rgba(255, 0, 0, 0.1) 17px
  );
}
```

## Quick Spacing Decisions

### For Dense Interfaces
- Base: 4px grid
- Components: 8-12px padding
- Gaps: 4-8px
- Sections: 16-24px

### For Reading-Focused
- Base: 8px grid
- Paragraphs: 1.5-1.7em line height
- Margins: 1.5em between blocks
- Max width: 65-75 characters

### For Marketing/Landing
- Base: 8px grid
- Sections: 80-120px padding
- Components: 24-32px padding
- Generous white space (30-40%)

### For Documentation
- Base: 8px grid
- Code blocks: 16px padding
- Headings: 2em top margin
- Lists: 0.5em between items