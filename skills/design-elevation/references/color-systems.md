# Color Systems & Palettes

Professional color systems built on **Tailwind CSS** as the canonical design token system. All color decisions should reference Tailwind's palette first.

## Core Principle

Color should **label**, **measure**, **represent**, or **highlight** — never merely decorate (Tufte). Apply the 60-30-10 rule: 60% neutrals, 30% secondary, 10% accent.

## Tailwind Neutral Foundations (Primary System)

### Gray Scale (Default — cool blue undertone)
Use `gray` as the default neutral. Choose `slate`, `zinc`, `neutral`, or `stone` only when temperature matters.

```css
/* Tailwind gray — the default for all text and backgrounds */
gray-50:  #F9FAFB;    /* bg-gray-50   — subtle backgrounds */
gray-100: #F3F4F6;    /* bg-gray-100  — card backgrounds, hover states */
gray-200: #E5E7EB;    /* border-gray-200 — default borders */
gray-300: #D1D5DB;    /* border-gray-300 — heavier borders */
gray-400: #9CA3AF;    /* text-gray-400 — tertiary text, placeholders */
gray-500: #6B7280;    /* text-gray-500 — secondary text */
gray-600: #4B5563;    /* text-gray-600 — strong secondary text */
gray-700: #374151;    /* text-gray-700 — subheadings */
gray-800: #1F2937;    /* text-gray-800 — near-black text */
gray-900: #111827;    /* text-gray-900 — primary text (NOT #000000) */
gray-950: #030712;    /* text-gray-950 — deepest dark mode backgrounds */
```

### Neutral Temperature Variants (Tailwind)
```
slate  — Cool/blue undertone   → Technical, corporate
gray   — Balanced cool         → Default, versatile
zinc   — True neutral          → Minimal, modern
neutral — Warm-ish neutral     → Approachable
stone  — Warm/brown undertone  → Organic, editorial
```

### Text & Background Pairings
```css
/* Light mode defaults */
--text-primary:   gray-900;    /* Main text */
--text-secondary: gray-500;    /* Supporting text */
--text-tertiary:  gray-400;    /* Captions, metadata */
--bg-primary:     white;       /* Main background */
--bg-secondary:   gray-50;     /* Subtle card/section backgrounds */
--bg-tertiary:    gray-100;    /* Hover states, grouped backgrounds */
--border-default: gray-200;    /* Subtle borders */
--border-heavy:   gray-300;    /* Emphasized borders */
```

## Tailwind Brand Colors (Semantic System)

### Primary Accent Options
Pick ONE as your primary accent. Use its `500` for standard, `600` for hover, `100` for subtle backgrounds.

```css
/* Blue — Professional, trustworthy (default choice) */
blue-500:    #3B82F6;   /* text-blue-500, bg-blue-500 */
blue-600:    #2563EB;   /* hover states */
blue-100:    #DBEAFE;   /* subtle backgrounds */

/* Indigo — Technical, modern */
indigo-500:  #6366F1;
indigo-600:  #4F46E5;

/* Violet — Creative, premium */
violet-500:  #8B5CF6;
violet-600:  #7C3AED;

/* Emerald — Growth, success */
emerald-500: #10B981;
emerald-600: #059669;

/* Cyan — Fresh, data-forward */
cyan-500:    #06B6D4;
cyan-600:    #0891B2;
```

### Semantic Colors (Tailwind)
```css
/* Status colors — consistent across all outputs */
--success:  emerald-500  (#10B981);  /* Positive, growth, complete */
--warning:  amber-500    (#F59E0B);  /* Caution, attention needed */
--error:    rose-500     (#F43F5E);  /* Error, negative, danger */
--info:     blue-500     (#3B82F6);  /* Information, neutral status */
```

## Dark Mode (Tailwind)

```css
/* Dark mode — swap light/dark values */
--text-primary:   gray-50;     /* Light text on dark */
--text-secondary: gray-400;
--text-tertiary:  gray-500;
--bg-primary:     gray-950;    /* Deepest background */
--bg-secondary:   gray-900;    /* Card backgrounds */
--bg-tertiary:    gray-800;    /* Hover states */
--border-default: gray-700;    /* Borders in dark mode use rgba(255,255,255,0.08) */
```

## Data Visualization Palettes (Tailwind-Native)

### Tufte's Color Principle
> Color should label, measure, represent, or highlight — never merely decorate.

Default to grays. Add color only when it encodes meaning. The most powerful technique: gray everything out, highlight one series in color.

### Categorical (Distinct — max 6-8)
Built from Tailwind's `500` shade for sufficient contrast on white:
```css
--cat-1: blue-500;     /* #3B82F6 */
--cat-2: emerald-500;  /* #10B981 */
--cat-3: amber-500;    /* #F59E0B */
--cat-4: violet-500;   /* #8B5CF6 */
--cat-5: rose-500;     /* #F43F5E */
--cat-6: cyan-500;     /* #06B6D4 */
--cat-7: orange-500;   /* #F97316 — use sparingly beyond 6 */
--cat-8: pink-500;     /* #EC4899 — use sparingly beyond 6 */
```

Use `400` for secondary emphasis, `600` for dark backgrounds.
Above 6 categories: use small multiples instead of more colors.

### Sequential (Gradient — single hue)
Use one Tailwind hue, stepping through shades for magnitude:
```css
/* Blue sequential — lightest = lowest, darkest = highest */
--seq-1: blue-50;    /* #EFF6FF */
--seq-2: blue-100;   /* #DBEAFE */
--seq-3: blue-200;   /* #BFDBFE */
--seq-4: blue-300;   /* #93C5FD */
--seq-5: blue-500;   /* #3B82F6 */
--seq-6: blue-700;   /* #1D4ED8 */
--seq-7: blue-900;   /* #1E3A8A */
```

Alternative hues: `emerald` for positive metrics, `rose` for risk/heat.

### Diverging (Two-direction)
Show deviation from a midpoint using two Tailwind hues through a neutral center:
```css
/* Rose ← Gray → Emerald (negative to positive) */
--div-neg-3: rose-700;     /* #BE123C */
--div-neg-2: rose-500;     /* #F43F5E */
--div-neg-1: rose-200;     /* #FECDD3 */
--div-mid:   gray-100;     /* #F3F4F6 */
--div-pos-1: emerald-200;  /* #A7F3D0 */
--div-pos-2: emerald-500;  /* #10B981 */
--div-pos-3: emerald-700;  /* #047857 */
```

### The Highlight Pattern
The single most effective dataviz color technique:
```html
<!-- Gray out everything, highlight the finding -->
<line class="text-gray-300" />  <!-- Series A -->
<line class="text-gray-300" />  <!-- Series B -->
<line class="text-blue-600" />  <!-- Series C: THE STORY -->
<line class="text-gray-300" />  <!-- Series D -->
```

### Accessibility in Data Color
- Never use color alone to encode meaning — pair with shape, pattern, or direct label
- Minimum 3:1 contrast ratio for graphical elements against background
- Avoid red/green as the only distinguishing pair (deuteranopia)
- Use Tailwind `500`+ shades on white for sufficient contrast
- Provide text alternatives: direct labels, data tables, or alt text

## Industry-Specific Palettes

### Finance/Banking
```css
--finance-primary: #003D5B;    /* Deep blue */
--finance-secondary: #00638D;  /* Mid blue */
--finance-accent: #30BCED;     /* Light blue */
--finance-success: #2A9D8F;    /* Teal */
--finance-warning: #E9C46A;    /* Gold */
--finance-error: #E76F51;      /* Coral */
--finance-neutral: #264653;    /* Dark gray */
```

### Healthcare
```css
--health-primary: #0077B6;     /* Medical blue */
--health-secondary: #00B4D8;   /* Light blue */
--health-accent: #90E0EF;      /* Pale blue */
--health-success: #52B788;     /* Green */
--health-warning: #FFB700;     /* Amber */
--health-error: #D00000;       /* Red */
--health-neutral: #495057;     /* Gray */
```

### Technology
```css
--tech-primary: #6366F1;       /* Indigo */
--tech-secondary: #8B5CF6;     /* Purple */
--tech-accent: #EC4899;        /* Pink */
--tech-success: #10B981;       /* Emerald */
--tech-warning: #F59E0B;       /* Amber */
--tech-error: #EF4444;         /* Red */
--tech-neutral: #64748B;       /* Slate */
```

### Education
```css
--edu-primary: #2563EB;        /* Blue */
--edu-secondary: #7C3AED;      /* Violet */
--edu-accent: #F59E0B;         /* Amber */
--edu-success: #10B981;        /* Green */
--edu-warning: #F97316;        /* Orange */
--edu-error: #DC2626;          /* Red */
--edu-neutral: #6B7280;        /* Gray */
```

## Gradient Systems

### Linear Gradients
```css
/* Subtle */
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);

/* Vibrant */
background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);

/* Professional */
background: linear-gradient(135deg, #13547a 0%, #80d0c7 100%);

/* Warm */
background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);

/* Cool */
background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
```

### Mesh Gradients
```css
/* Modern mesh gradient */
background: 
  radial-gradient(at 40% 20%, hsla(28,100%,74%,1) 0px, transparent 50%),
  radial-gradient(at 80% 0%, hsla(189,100%,56%,1) 0px, transparent 50%),
  radial-gradient(at 0% 50%, hsla(355,100%,93%,1) 0px, transparent 50%),
  radial-gradient(at 80% 100%, hsla(340,100%,76%,1) 0px, transparent 50%),
  radial-gradient(at 0% 100%, hsla(22,100%,77%,1) 0px, transparent 50%),
  radial-gradient(at 0% 0%, hsla(242,100%,70%,1) 0px, transparent 50%);
```

## Accessibility Color Combinations

### WCAG AAA Compliant
```css
/* Dark on Light */
--text: #000000;
--background: #FFFFFF;
/* Contrast ratio: 21:1 */

/* Blue on White */
--text: #003D82;
--background: #FFFFFF;
/* Contrast ratio: 11.5:1 */

/* White on Dark Blue */
--text: #FFFFFF;
--background: #003D82;
/* Contrast ratio: 11.5:1 */
```

### WCAG AA Compliant
```css
/* Gray on White */
--text: #595959;
--background: #FFFFFF;
/* Contrast ratio: 7:1 */

/* Blue on Light Gray */
--text: #0066CC;
--background: #F5F5F5;
/* Contrast ratio: 5.4:1 */
```

## Color Application Strategies

### Monochromatic Sophistication
```css
/* Use single hue with varied saturation/lightness */
--mono-100: hsl(220, 60%, 95%);
--mono-200: hsl(220, 60%, 85%);
--mono-300: hsl(220, 60%, 70%);
--mono-400: hsl(220, 60%, 55%);
--mono-500: hsl(220, 60%, 40%);
--mono-600: hsl(220, 60%, 30%);
--mono-700: hsl(220, 60%, 20%);
--mono-800: hsl(220, 60%, 10%);
```

### Analogous Harmony
```css
/* Adjacent colors for cohesion */
--primary: hsl(200, 70%, 50%);    /* Blue */
--secondary: hsl(180, 70%, 50%);  /* Cyan */
--tertiary: hsl(220, 70%, 50%);   /* Blue-violet */
```

### Triadic Energy
```css
/* Three equidistant colors */
--primary: hsl(10, 80%, 50%);     /* Red-orange */
--secondary: hsl(130, 80%, 50%);  /* Green */
--tertiary: hsl(250, 80%, 50%);   /* Blue-violet */
```

## Shadow Color Systems

### Colored Shadows
```css
/* Blue tinted shadows */
box-shadow: 
  0 1px 3px rgba(59, 130, 246, 0.15),
  0 1px 2px rgba(59, 130, 246, 0.3);

/* Warm shadows */
box-shadow: 
  0 4px 6px rgba(139, 92, 78, 0.07),
  0 1px 3px rgba(139, 92, 78, 0.12);

/* Purple glow */
box-shadow: 
  0 0 20px rgba(139, 92, 246, 0.2),
  0 0 40px rgba(139, 92, 246, 0.1);
```

## Quick Color Decisions

### For "Professional/Corporate"
- Primary: Deep blue (#003D82)
- Neutrals: Cool grays
- Accent: Minimal, muted

### For "Modern/Tech"
- Primary: Indigo/Purple gradient
- Neutrals: True neutrals
- Accent: Bright, electric

### For "Friendly/Approachable"
- Primary: Teal or green
- Neutrals: Warm grays
- Accent: Orange or yellow

### For "Luxury/Premium"
- Primary: Deep purple or burgundy
- Neutrals: Rich blacks
- Accent: Gold or copper