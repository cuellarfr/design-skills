# Color Systems & Palettes

Professional color systems for creating sophisticated, cohesive visual designs.

## Color Theory Fundamentals

### Color Relationships
```
Monochromatic: Single hue, varied saturation/lightness
Analogous: Adjacent hues (30-60° apart)
Complementary: Opposite hues (180° apart)
Split-Complementary: Main + two adjacent to complement
Triadic: Three equidistant hues (120° apart)
Tetradic: Four hues in complementary pairs
```

### The 60-30-10 Rule
```
60% - Dominant color (usually neutral)
30% - Secondary color (supporting)
10% - Accent color (emphasis)

Example:
60% - Light gray backgrounds
30% - Dark gray text
10% - Blue CTAs and links
```

## Neutral Foundations

### Sophisticated Grays
```css
/* Cool Grays (blue undertone) */
--gray-50:  #F9FAFB;
--gray-100: #F3F4F6;
--gray-200: #E5E7EB;
--gray-300: #D1D5DB;
--gray-400: #9CA3AF;
--gray-500: #6B7280;
--gray-600: #4B5563;
--gray-700: #374151;
--gray-800: #1F2937;
--gray-900: #111827;

/* Warm Grays (brown undertone) */
--stone-50:  #FAFAF9;
--stone-100: #F5F5F4;
--stone-200: #E7E5E4;
--stone-300: #D6D3D1;
--stone-400: #A8A29E;
--stone-500: #78716C;
--stone-600: #57534E;
--stone-700: #44403C;
--stone-800: #292524;
--stone-900: #1C1917;

/* True Neutrals */
--neutral-50:  #FAFAFA;
--neutral-100: #F5F5F5;
--neutral-200: #E5E5E5;
--neutral-300: #D4D4D4;
--neutral-400: #A3A3A3;
--neutral-500: #737373;
--neutral-600: #525252;
--neutral-700: #404040;
--neutral-800: #262626;
--neutral-900: #171717;
```

### Premium Black & White
```css
/* Never use pure black/white */
--black: #0A0A0A;        /* Not #000000 */
--off-black: #1A1A1A;
--rich-black: #0D1117;   /* GitHub dark */
--ink-black: #0C0A09;    /* Warm black */

--white: #FFFFFF;        /* Only for pure needs */
--off-white: #FAFAFA;
--cream: #FFFDF7;
--pearl: #FCFCFC;
```

## Brand Color Systems

### Corporate Blue
```css
--blue-50:  #EFF6FF;
--blue-100: #DBEAFE;
--blue-200: #BFDBFE;
--blue-300: #93C5FD;
--blue-400: #60A5FA;
--blue-500: #3B82F6;  /* Primary */
--blue-600: #2563EB;
--blue-700: #1D4ED8;
--blue-800: #1E40AF;
--blue-900: #1E3A8A;
```

### Success Green
```css
--green-50:  #F0FDF4;
--green-100: #DCFCE7;
--green-200: #BBF7D0;
--green-300: #86EFAC;
--green-400: #4ADE80;
--green-500: #22C55E;  /* Primary */
--green-600: #16A34A;
--green-700: #15803D;
--green-800: #166534;
--green-900: #14532D;
```

### Warning Amber
```css
--amber-50:  #FFFBEB;
--amber-100: #FEF3C7;
--amber-200: #FDE68A;
--amber-300: #FCD34D;
--amber-400: #FBBF24;
--amber-500: #F59E0B;  /* Primary */
--amber-600: #D97706;
--amber-700: #B45309;
--amber-800: #92400E;
--amber-900: #78350F;
```

### Error Red
```css
--red-50:  #FEF2F2;
--red-100: #FEE2E2;
--red-200: #FECACA;
--red-300: #FCA5A5;
--red-400: #F87171;
--red-500: #EF4444;  /* Primary */
--red-600: #DC2626;
--red-700: #B91C1C;
--red-800: #991B1B;
--red-900: #7F1D1D;
```

## Semantic Color Systems

### Light Mode Semantics
```css
/* Backgrounds */
--bg-primary: var(--white);
--bg-secondary: var(--gray-50);
--bg-tertiary: var(--gray-100);
--bg-inverse: var(--gray-900);

/* Text */
--text-primary: var(--gray-900);
--text-secondary: var(--gray-600);
--text-tertiary: var(--gray-400);
--text-inverse: var(--white);

/* Borders */
--border-light: var(--gray-200);
--border-medium: var(--gray-300);
--border-heavy: var(--gray-400);

/* States */
--state-hover: rgba(0, 0, 0, 0.04);
--state-active: rgba(0, 0, 0, 0.08);
--state-focus: var(--blue-500);
--state-disabled: var(--gray-300);
```

### Dark Mode Semantics
```css
/* Backgrounds */
--bg-primary: var(--gray-900);
--bg-secondary: var(--gray-800);
--bg-tertiary: var(--gray-700);
--bg-inverse: var(--gray-50);

/* Text */
--text-primary: var(--gray-50);
--text-secondary: var(--gray-300);
--text-tertiary: var(--gray-500);
--text-inverse: var(--gray-900);

/* Borders */
--border-light: var(--gray-700);
--border-medium: var(--gray-600);
--border-heavy: var(--gray-500);

/* States */
--state-hover: rgba(255, 255, 255, 0.04);
--state-active: rgba(255, 255, 255, 0.08);
--state-focus: var(--blue-400);
--state-disabled: var(--gray-600);
```

## Data Visualization Palettes

### Categorical (Distinct)
```css
--data-1: #5B8FF9;  /* Blue */
--data-2: #61DDAA;  /* Teal */
--data-3: #65789B;  /* Gray Blue */
--data-4: #F6BD16;  /* Yellow */
--data-5: #7262FD;  /* Purple */
--data-6: #78D3F8;  /* Light Blue */
--data-7: #9661BC;  /* Violet */
--data-8: #F6903D;  /* Orange */
--data-9: #008685;  /* Dark Teal */
--data-10: #F08BB4; /* Pink */
```

### Sequential (Gradient)
```css
/* Blue gradient for continuous data */
--seq-1: #F0F9FF;
--seq-2: #E0F2FE;
--seq-3: #BAE6FD;
--seq-4: #7DD3FC;
--seq-5: #38BDF8;
--seq-6: #0EA5E9;
--seq-7: #0284C7;
--seq-8: #0369A1;
--seq-9: #075985;
```

### Diverging (Two-direction)
```css
/* Red to Blue through White */
--div-1: #B91C1C;
--div-2: #DC2626;
--div-3: #F87171;
--div-4: #FCA5A5;
--div-5: #FFFFFF;
--div-6: #93C5FD;
--div-7: #60A5FA;
--div-8: #2563EB;
--div-9: #1D4ED8;
```

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