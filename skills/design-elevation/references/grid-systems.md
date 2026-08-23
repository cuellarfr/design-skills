# Grid Systems & Layout Structures

Professional grid systems for creating organized, balanced layouts across different media.

## Foundation Grid Systems

### 8-Point Grid System
```css
/* Base unit: 8px */
--space-1: 8px;
--space-2: 16px;
--space-3: 24px;
--space-4: 32px;
--space-5: 40px;
--space-6: 48px;
--space-8: 64px;
--space-10: 80px;
--space-12: 96px;
--space-16: 128px;
--space-20: 160px;
--space-24: 192px;
--space-32: 256px;

/* Usage */
padding: var(--space-2) var(--space-3);
margin-bottom: var(--space-4);
gap: var(--space-2);
```

### 4-Point Grid System (Dense)
```css
/* For compact interfaces */
--space-1: 4px;
--space-2: 8px;
--space-3: 12px;
--space-4: 16px;
--space-5: 20px;
--space-6: 24px;
--space-8: 32px;
--space-10: 40px;
--space-12: 48px;
```

## Column Grid Systems

### 12-Column Grid
```css
/* Classic, versatile grid */
.grid-12 {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: 24px;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 24px;
}

/* Common patterns */
.col-span-12 { grid-column: span 12; } /* Full width */
.col-span-8 { grid-column: span 8; }   /* Main content */
.col-span-6 { grid-column: span 6; }   /* Half */
.col-span-4 { grid-column: span 4; }   /* Sidebar */
.col-span-3 { grid-column: span 3; }   /* Quarter */
```

### 16-Column Grid (Complex)
```css
/* For sophisticated layouts */
.grid-16 {
  display: grid;
  grid-template-columns: repeat(16, 1fr);
  gap: 20px;
  max-width: 1440px;
  margin: 0 auto;
}

/* Content regions */
.main { grid-column: 3 / 15; }      /* Central content */
.wide { grid-column: 2 / 16; }      /* Wide content */
.narrow { grid-column: 5 / 13; }    /* Reading width */
```

### Asymmetric Grid
```css
/* For dynamic layouts */
.grid-asymmetric {
  display: grid;
  grid-template-columns: 2fr 3fr 2fr 5fr 3fr;
  gap: 32px;
}

/* Golden ratio grid */
.grid-golden {
  display: grid;
  grid-template-columns: 1fr 1.618fr;
  gap: 40px;
}
```

## Responsive Grid Systems

### Fluid Grid
```css
.fluid-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 24px;
}

/* With maximum columns */
.fluid-grid-max {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 32px;
  max-width: 1400px;
}
```

### Responsive Breakpoint Grid
```css
.responsive-grid {
  display: grid;
  gap: 16px;
  
  /* Mobile: 1 column */
  grid-template-columns: 1fr;
}

@media (min-width: 640px) {
  .responsive-grid {
    /* Tablet: 2 columns */
    grid-template-columns: repeat(2, 1fr);
    gap: 24px;
  }
}

@media (min-width: 1024px) {
  .responsive-grid {
    /* Desktop: 3 columns */
    grid-template-columns: repeat(3, 1fr);
    gap: 32px;
  }
}

@media (min-width: 1440px) {
  .responsive-grid {
    /* Wide: 4 columns */
    grid-template-columns: repeat(4, 1fr);
    gap: 40px;
  }
}
```

## Specialized Grid Patterns

### Dashboard Grid
```css
.dashboard-grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  grid-auto-rows: 100px;
  gap: 16px;
  padding: 16px;
}

/* Widget sizes */
.widget-small { 
  grid-column: span 3;
  grid-row: span 1;
}

.widget-medium { 
  grid-column: span 6;
  grid-row: span 2;
}

.widget-large { 
  grid-column: span 9;
  grid-row: span 3;
}

.widget-full { 
  grid-column: span 12;
  grid-row: span 2;
}
```

### Magazine Layout Grid
```css
.magazine-grid {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  grid-auto-rows: minmax(100px, auto);
  gap: 24px;
}

/* Article layouts */
.feature-article {
  grid-column: span 4;
  grid-row: span 3;
}

.sidebar-article {
  grid-column: span 2;
  grid-row: span 2;
}

.quote-block {
  grid-column: 2 / 6;
  grid-row: span 1;
}
```

### Card Grid System
```css
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 24px;
  align-items: start;
}

/* Featured card */
.card-featured {
  grid-column: span 2;
  grid-row: span 2;
}

/* Masonry effect */
.card-grid-masonry {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-rows: 20px;
  gap: 20px;
}

.card-tall { grid-row: span 15; }
.card-medium { grid-row: span 10; }
.card-short { grid-row: span 8; }
```

## Presentation Grids

### Slide Grid (16:9)
```
Standard presentation grid:
- 12 columns
- 8 rows
- 40px margins
- 20px gutters

Safe area: 10-90% of slide
Title zone: Top 20%
Content zone: 20-85%
Footer zone: Bottom 10%
```

### Slide Layouts
```css
/* Title slide */
.slide-title {
  display: grid;
  place-items: center;
  min-height: 100vh;
  text-align: center;
}

/* Content slide */
.slide-content {
  display: grid;
  grid-template-rows: auto 1fr auto;
  gap: 40px;
  padding: 60px;
  min-height: 100vh;
}

/* Two-column slide */
.slide-two-col {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 60px;
  padding: 60px;
  align-items: center;
}

/* Image + text slide */
.slide-image-text {
  display: grid;
  grid-template-columns: 3fr 2fr;
  gap: 80px;
  align-items: center;
}
```

## Document Grids

### A4 Document Grid
```css
.document-a4 {
  width: 210mm;
  min-height: 297mm;
  padding: 25mm 20mm;
  display: grid;
  grid-template-rows: auto 1fr auto;
}

/* Multi-column text */
.document-columns {
  column-count: 2;
  column-gap: 20mm;
  column-rule: 1px solid #e5e5e5;
}
```

### Report Layout Grid
```css
.report-grid {
  display: grid;
  grid-template-columns: 200px 1fr;
  gap: 40px;
  max-width: 1200px;
  margin: 0 auto;
}

/* Sections */
.report-sidebar {
  position: sticky;
  top: 20px;
  height: fit-content;
}

.report-content {
  display: grid;
  gap: 60px;
}

.report-section {
  display: grid;
  gap: 24px;
}
```

## Spacing Systems

### Fibonacci Spacing
```css
:root {
  --fib-1: 1px;
  --fib-2: 2px;
  --fib-3: 3px;
  --fib-5: 5px;
  --fib-8: 8px;
  --fib-13: 13px;
  --fib-21: 21px;
  --fib-34: 34px;
  --fib-55: 55px;
  --fib-89: 89px;
  --fib-144: 144px;
}
```

### Modular Scale Spacing
```css
/* Based on 1.5x ratio */
:root {
  --space-xs: 4px;    /* 0.25rem */
  --space-s: 6px;     /* 0.375rem */
  --space-m: 9px;     /* 0.5625rem */
  --space-l: 14px;    /* 0.875rem */
  --space-xl: 21px;   /* 1.3125rem */
  --space-2xl: 31px;  /* 1.9375rem */
  --space-3xl: 47px;  /* 2.9375rem */
  --space-4xl: 70px;  /* 4.375rem */
}
```

### Proportional Spacing
```css
/* Based on font size */
.proportional-spacing {
  padding: 1em 1.5em;
  margin: 2em 0;
  gap: 0.75em;
}

/* Based on element width */
.width-based {
  padding: 5%;
  margin: 10% auto;
}
```

## Layout Composition Patterns

### The Rule of Thirds
```css
.rule-of-thirds {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: 1fr 1fr 1fr;
}

/* Place focal points at intersections */
.focal-point {
  grid-column: 2;
  grid-row: 2;
}
```

### Golden Rectangle Layout
```css
.golden-layout {
  display: grid;
  grid-template-columns: 1fr 1.618fr;
  min-height: 100vh;
}

/* Recursive golden rectangles */
.golden-recursive {
  display: grid;
  grid-template-columns: 1.618fr 1fr;
  grid-template-rows: 1fr 1.618fr;
}
```

### Swiss Poster Grid
```css
.swiss-grid {
  display: grid;
  grid-template-columns: repeat(8, 1fr);
  grid-template-rows: repeat(12, 1fr);
  gap: 0;
  height: 100vh;
}

/* Typical Swiss placements */
.swiss-title {
  grid-column: 1 / 7;
  grid-row: 2 / 4;
}

.swiss-body {
  grid-column: 1 / 5;
  grid-row: 5 / 10;
}

.swiss-image {
  grid-column: 5 / 9;
  grid-row: 4 / 11;
}
```

## Container & Margin Systems

### Container Widths
```css
.container-xs { max-width: 640px; }   /* Mobile reading */
.container-sm { max-width: 768px; }   /* Tablet */
.container-md { max-width: 1024px; }  /* Small desktop */
.container-lg { max-width: 1280px; }  /* Desktop */
.container-xl { max-width: 1440px; }  /* Wide desktop */
.container-2xl { max-width: 1680px; } /* Ultra-wide */
.container-full { max-width: 100%; }  /* Full width */
```

### Responsive Margins
```css
.responsive-container {
  width: 100%;
  margin: 0 auto;
  padding: 0 16px;
}

@media (min-width: 640px) {
  .responsive-container {
    padding: 0 24px;
  }
}

@media (min-width: 1024px) {
  .responsive-container {
    padding: 0 40px;
  }
}

@media (min-width: 1440px) {
  .responsive-container {
    padding: 0 80px;
  }
}
```

## Grid Debugging

### Visual Grid Overlay
```css
.show-grid {
  background-image: 
    repeating-linear-gradient(
      90deg,
      rgba(255, 0, 0, 0.1) 0,
      rgba(255, 0, 0, 0.1) 1px,
      transparent 1px,
      transparent 8.333%
    ),
    repeating-linear-gradient(
      0deg,
      rgba(255, 0, 0, 0.1) 0,
      rgba(255, 0, 0, 0.1) 1px,
      transparent 1px,
      transparent 100px
    );
}
```

## Quick Grid Selection

### For Presentations
- 12-column grid
- 40-60px margins
- 16-24px gutters
- 8-point spacing system

### For Dashboards
- 12 or 24-column grid
- 16px gutters
- 4-point spacing system
- Flexible row heights

### For Documents
- 2-3 column options
- 1 inch margins minimum
- 0.5 inch gutters
- Baseline grid alignment

### For Web Pages
- 12-column responsive
- Fluid or fixed max-width
- 20-40px gutters
- 8-point spacing system