# Typography Scales & Systems

Comprehensive typography systems for different contexts and applications.

## Modular Scale Systems

### Minor Second (1.067x)
**Use for**: Dense interfaces, data-heavy applications
```
Base: 16px
Scale: 16, 17, 18, 19, 21, 22, 23, 25, 26, 28
Application: Dashboards, tables, compact UIs
```

### Major Second (1.125x)
**Use for**: Subtle hierarchy, reading-focused
```
Base: 16px
Scale: 16, 18, 20, 23, 25, 29, 32, 36, 40, 45
Application: Articles, documentation, blogs
```

### Minor Third (1.2x)
**Use for**: Balanced hierarchy, versatile
```
Base: 16px
Scale: 16, 19, 23, 28, 33, 40, 48, 58, 69, 83
Application: Marketing sites, presentations
```

### Major Third (1.25x)
**Use for**: Clear hierarchy, standard choice
```
Base: 16px
Scale: 16, 20, 25, 31, 39, 49, 61, 76, 95, 119
Application: Most web applications
```

### Perfect Fourth (1.333x)
**Use for**: Strong contrast, editorial
```
Base: 16px
Scale: 16, 21, 28, 38, 50, 67, 89, 119, 158
Application: Magazines, bold websites
```

### Perfect Fifth (1.5x)
**Use for**: Dramatic hierarchy, minimal text
```
Base: 16px
Scale: 16, 24, 36, 54, 81, 121, 182
Application: Posters, landing pages
```

### Golden Ratio (1.618x)
**Use for**: Natural harmony, artistic
```
Base: 16px
Scale: 16, 26, 42, 68, 110, 178
Application: Luxury brands, portfolios
```

## Responsive Typography Systems

### Fluid Typography
```css
/* Headline */
h1 {
  font-size: clamp(2rem, 5vw + 1rem, 4rem);
  line-height: clamp(2.2rem, 5vw + 1.2rem, 4.4rem);
}

/* Subheadline */
h2 {
  font-size: clamp(1.5rem, 3vw + 0.5rem, 2.5rem);
  line-height: clamp(1.8rem, 3vw + 0.8rem, 3rem);
}

/* Body */
p {
  font-size: clamp(1rem, 2vw + 0.25rem, 1.25rem);
  line-height: clamp(1.5rem, 2vw + 0.75rem, 1.875rem);
}
```

### Breakpoint-Based System
```css
/* Mobile First */
body { font-size: 16px; }
h1 { font-size: 32px; }
h2 { font-size: 24px; }
h3 { font-size: 20px; }

/* Tablet */
@media (min-width: 768px) {
  body { font-size: 18px; }
  h1 { font-size: 48px; }
  h2 { font-size: 36px; }
  h3 { font-size: 24px; }
}

/* Desktop */
@media (min-width: 1024px) {
  body { font-size: 20px; }
  h1 { font-size: 64px; }
  h2 { font-size: 48px; }
  h3 { font-size: 32px; }
}
```

## Professional Type Systems

### Corporate System
```
Display: 48-72px, Light 300, -0.02em tracking
Headline: 32-40px, Regular 400, -0.01em tracking
Title: 24-28px, Medium 500, 0 tracking
Subtitle: 18-20px, Medium 500, 0.01em tracking
Body: 15-17px, Regular 400, 0 tracking
Caption: 13-14px, Regular 400, 0.02em tracking
Overline: 11-12px, Medium 500, 0.08em tracking, uppercase
```

### Editorial System
```
Display: 60-96px, Serif, Light, 1.1 line-height
Headline: 36-48px, Serif, Regular, 1.2 line-height
Subhead: 21-24px, Sans-serif, Medium, 1.4 line-height
Body: 18-20px, Serif, Regular, 1.6 line-height
Lead: 21-24px, Serif, Regular, 1.5 line-height
Caption: 14-15px, Sans-serif, Regular, 1.4 line-height
Pull Quote: 28-32px, Serif, Light Italic, 1.3 line-height
```

### Technical Documentation
```
Title: 32px, Sans-serif, Bold, 1.2 line-height
Section: 24px, Sans-serif, Semibold, 1.3 line-height
Subsection: 18px, Sans-serif, Medium, 1.4 line-height
Body: 16px, Sans-serif, Regular, 1.6 line-height
Code Inline: 14px, Monospace, Regular, 1.5 line-height
Code Block: 14px, Monospace, Regular, 1.6 line-height
Table: 14px, Sans-serif, Regular, 1.4 line-height
Footnote: 12px, Sans-serif, Regular, 1.4 line-height
```

### Dashboard Typography
```
KPI Number: 48-64px, Tabular figures, Medium
KPI Label: 12-14px, Uppercase, 0.08em tracking
Card Title: 16-18px, Semibold
Card Body: 14px, Regular
Table Header: 12px, Medium, Uppercase, 0.05em tracking
Table Cell: 14px, Regular
Chart Label: 11px, Regular
Tooltip: 12px, Regular
```

## Font Loading Strategies

### Performance-First Stack
```css
font-family: 
  -apple-system,           /* Safari Mac */
  BlinkMacSystemFont,      /* Chrome Mac */
  "Segoe UI",             /* Windows */
  Roboto,                 /* Android */
  Oxygen,                 /* KDE */
  Ubuntu,                 /* Ubuntu */
  "Helvetica Neue",       /* Fallback */
  Arial,                  /* Fallback */
  sans-serif;            /* Generic */
```

### Variable Font Loading
```css
@font-face {
  font-family: 'Inter';
  font-weight: 100 900;
  font-display: swap;
  src: url('Inter.woff2') format('woff2-variations');
}

body {
  font-family: 'Inter', sans-serif;
  font-weight: 400;
  font-variation-settings: 'wght' 400;
}

strong {
  font-variation-settings: 'wght' 700;
}
```

## Advanced Typography Features

### OpenType Features
```css
/* Ligatures */
font-feature-settings: 'liga' 1, 'clig' 1;

/* Tabular figures for numbers */
font-variant-numeric: tabular-nums;

/* Small caps */
font-variant-caps: small-caps;

/* Fractions */
font-variant-numeric: diagonal-fractions;

/* Superscript/Subscript */
font-variant-position: super;
font-variant-position: sub;

/* Stylistic alternates */
font-feature-settings: 'salt' 1;
```

### Line Height Systems
```
Display text (>32px): 1.0 - 1.2
Headings (20-32px): 1.2 - 1.4
Body text (14-20px): 1.4 - 1.7
Small text (<14px): 1.3 - 1.5
Code blocks: 1.4 - 1.6
Tables: 1.2 - 1.4
```

### Letter Spacing Guidelines
```
Uppercase text: 0.05 - 0.15em
Display text (>48px): -0.02 - 0em
Headlines (24-48px): -0.01 - 0em
Body text: 0em (default)
Small text (<14px): 0 - 0.02em
Light weight text: 0.01 - 0.03em
Bold text: -0.01 - 0em
```

## Type Color Systems

### Contrast Hierarchy
```css
/* High contrast (primary content) */
.text-primary { color: rgba(0, 0, 0, 0.87); }

/* Medium contrast (secondary content) */
.text-secondary { color: rgba(0, 0, 0, 0.60); }

/* Low contrast (tertiary content) */
.text-tertiary { color: rgba(0, 0, 0, 0.38); }

/* Disabled state */
.text-disabled { color: rgba(0, 0, 0, 0.25); }

/* Dark mode equivalents */
.dark .text-primary { color: rgba(255, 255, 255, 0.87); }
.dark .text-secondary { color: rgba(255, 255, 255, 0.60); }
.dark .text-tertiary { color: rgba(255, 255, 255, 0.38); }
```

### Semantic Colors
```css
.text-success { color: #10B981; }
.text-warning { color: #F59E0B; }
.text-error { color: #EF4444; }
.text-info { color: #3B82F6; }
.text-muted { color: #6B7280; }
```

## Measure & Readability

### Optimal Line Length
```
45-75 characters per line (optimal: 66)
Mobile: 30-40 characters
Tablet: 50-75 characters
Desktop: 60-80 characters
Wide screen: Constrain to max-width
```

### Paragraph Spacing
```css
p + p { margin-top: 1em; }          /* Between paragraphs */
h2 + p { margin-top: 0.5em; }       /* After headings */
p + h2 { margin-top: 2em; }         /* Before headings */
li + li { margin-top: 0.25em; }     /* List items */
blockquote { margin: 2em 0; }       /* Blockquotes */
```

## Special Typography Patterns

### Drop Caps
```css
.drop-cap::first-letter {
  font-size: 4em;
  line-height: 1;
  float: left;
  margin: 0 0.1em 0 0;
  font-weight: bold;
}
```

### Pull Quotes
```css
.pull-quote {
  font-size: 1.5em;
  line-height: 1.4;
  margin: 2em 0;
  padding: 1em 0;
  border-top: 3px solid #000;
  border-bottom: 3px solid #000;
  font-style: italic;
}
```

### Hanging Punctuation
```css
.hanging-punctuation {
  text-indent: -0.4em;
  padding-left: 0.4em;
}
```

### Small Caps
```css
.small-caps {
  font-variant: small-caps;
  letter-spacing: 0.05em;
}
```

## Quick Selection Guide

### For Corporate/Professional
- Font: Inter, Helvetica Neue, SF Pro
- Scale: Major Third (1.25x)
- Weights: 400, 500, 600
- Line Height: 1.5-1.6

### For Editorial/Magazine
- Font: Tiempos + Graphik
- Scale: Perfect Fourth (1.333x)
- Weights: 300, 400, 700
- Line Height: 1.6-1.8

### For Technical/Developer
- Font: JetBrains Mono, SF Mono, Consolas
- Scale: Minor Third (1.2x)
- Weights: 400, 600
- Line Height: 1.4-1.5

### For Marketing/Sales
- Font: Circular, GT America
- Scale: Perfect Fifth (1.5x)
- Weights: 300, 400, 700, 900
- Line Height: 1.2-1.4