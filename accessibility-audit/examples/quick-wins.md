# Accessibility Quick Wins

The 20% of fixes that solve 80% of accessibility problems. Each fix is small effort, high impact. Sorted by expected improvement to your accessibility score.

---

## 1. Add `lang` to `<html>`

**Time:** 30 seconds
**WCAG:** 3.1.1 (A)
**Impact:** Screen readers use correct pronunciation rules for the entire page

```html
<!-- Before -->
<html>

<!-- After -->
<html lang="en">
```

If your page includes content in other languages:
```html
<p>The German word <span lang="de">Schadenfreude</span> has no English equivalent.</p>
```

---

## 2. Fix Color Contrast

**Time:** 15-30 minutes (site-wide)
**WCAG:** 1.4.3 (AA)
**Impact:** Readable text for low vision users, outdoor usage, aging population

**The safe text colors on white (#fff):**

| Use Case | Minimum Safe Color | Ratio |
|---|---|---|
| Body text | #595959 | 7.0:1 (passes AAA) |
| Secondary text | #767676 | 4.5:1 (passes AA) |
| Large text (18pt+) | #949494 | 3.0:1 (passes AA for large) |
| Placeholder text | #767676 | 4.5:1 (passes AA) |

**Quick fix:** Search your CSS for any color lighter than `#767676` used for text on white backgrounds. Darken them.

---

## 3. Add Labels to All Form Inputs

**Time:** 5-15 minutes per form
**WCAG:** 1.3.1 (A)
**Impact:** Screen reader users can identify every form field

**Pattern to use everywhere:**
```html
<label for="fieldname">Label text</label>
<input type="text" id="fieldname">
```

**Checklist:**
- Search code for `<input>` without matching `<label for="...">`
- Search for inputs relying on `placeholder` as the only label
- Search for `<textarea>` and `<select>` without labels

---

## 4. Add Alt Text to Images

**Time:** 2-5 minutes per page
**WCAG:** 1.1.1 (A)
**Impact:** Screen reader users understand image content

**Quick decision:**
- **Decorative?** → `alt=""`
- **Conveys information?** → Describe the content: `alt="Bar chart showing revenue grew 40% in Q3"`
- **Is a link/button?** → Describe the action: `alt="Download report as PDF"`

**Find all images missing alt:** Run axe DevTools or search code for `<img` without `alt=`.

---

## 5. Add a Skip Link

**Time:** 10 minutes
**WCAG:** 2.4.1 (A)
**Impact:** Keyboard users skip past navigation on every page

```html
<!-- First element inside <body> -->
<a href="#main" class="skip-link">Skip to main content</a>

<!-- Your navigation -->
<nav>...</nav>

<!-- Main content -->
<main id="main">...</main>
```

```css
.skip-link {
  position: absolute;
  top: -40px;
  left: 0;
  padding: 8px 16px;
  background: #000;
  color: #fff;
  z-index: 1000;
}
.skip-link:focus {
  top: 0;
}
```

---

## 6. Use Semantic Landmarks

**Time:** 10-20 minutes
**WCAG:** 1.3.1 (A)
**Impact:** Screen reader users can jump between page sections

Replace:
```html
<div class="header">...</div>
<div class="nav">...</div>
<div class="content">...</div>
<div class="sidebar">...</div>
<div class="footer">...</div>
```

With:
```html
<header>...</header>
<nav aria-label="Main">...</nav>
<main>...</main>
<aside>...</aside>
<footer>...</footer>
```

---

## 7. Fix Heading Hierarchy

**Time:** 10-15 minutes per page
**WCAG:** 1.3.1 (A)
**Impact:** Screen reader users navigate by heading structure

**Rules:**
- One `<h1>` per page (the page title)
- Never skip levels going down
- Use headings for structure, CSS for visual size

**Quick check:** Install the HeadingsMap browser extension — it shows your heading tree instantly.

---

## 8. Add Visible Focus Indicators

**Time:** 10 minutes
**WCAG:** 2.4.7 (AA)
**Impact:** Keyboard users can see where they are on the page

```css
/* One rule to fix the whole site */
:focus-visible {
  outline: 2px solid #1a73e8;
  outline-offset: 2px;
}
```

**Find and remove:** Search CSS for `outline: none` or `outline: 0`. Remove them, or replace with the rule above.

---

## 9. Make Icon Buttons Accessible

**Time:** 2 minutes per button
**WCAG:** 4.1.2 (A)
**Impact:** Screen reader users know what every button does

```html
<!-- Before: "button" with no name -->
<button><svg>...</svg></button>

<!-- After: accessible name via aria-label -->
<button aria-label="Close">
  <svg aria-hidden="true">...</svg>
</button>
```

**Find all:** Search for `<button>` elements that contain only `<svg>`, `<i>`, or `<img>` with no text content.

---

## 10. Add `aria-live` to Dynamic Messages

**Time:** 5 minutes per message type
**WCAG:** 4.1.3 (AA)
**Impact:** Screen reader users are informed of success, error, and loading states

```html
<!-- For success/info messages -->
<div role="status" aria-live="polite">Item added to cart</div>

<!-- For error/urgent messages -->
<div role="alert" aria-live="assertive">Payment failed. Please try again.</div>
```

---

## Quick Wins Cheat Sheet

| # | Fix | Time | WCAG | Effort |
|---|---|---|---|---|
| 1 | Add `lang` to `<html>` | 30 sec | 3.1.1 A | Trivial |
| 2 | Fix text contrast | 15-30 min | 1.4.3 AA | Small |
| 3 | Label all form inputs | 5-15 min/form | 1.3.1 A | Small |
| 4 | Add alt text to images | 2-5 min/page | 1.1.1 A | Small |
| 5 | Add skip link | 10 min | 2.4.1 A | Small |
| 6 | Use semantic landmarks | 10-20 min | 1.3.1 A | Small |
| 7 | Fix heading hierarchy | 10-15 min/page | 1.3.1 A | Small |
| 8 | Add visible focus indicators | 10 min | 2.4.7 AA | Small |
| 9 | Label icon buttons | 2 min/button | 4.1.2 A | Trivial |
| 10 | Add aria-live to messages | 5 min/type | 4.1.3 AA | Small |

**Total estimated time for all 10:** 2-4 hours for a typical site.
**Expected Lighthouse score improvement:** +20-30 points.
**WCAG issues resolved:** Typically 60-70% of all Level A and AA failures.
