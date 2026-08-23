# Common Accessibility Issues and Fixes

The 15 most frequent accessibility failures with before/after code examples. Ordered by prevalence (based on WebAIM Million analysis).

---

## 1. Low Text Contrast

**WCAG:** 1.4.3 (AA) | **Prevalence:** 83% of pages | **Severity:** High

The #1 accessibility issue on the web. Usually caused by light gray text on white, or colored text on colored backgrounds.

**Before (fails):**
```css
/* Gray text on white — ratio 2.7:1 */
.subtitle {
  color: #999999;
  background: #ffffff;
}
```

**After (passes):**
```css
/* Darkened gray — ratio 4.6:1 */
.subtitle {
  color: #595959;
  background: #ffffff;
}
```

**Quick reference:**

| Text Size | AA Minimum | AAA Minimum |
|---|---|---|
| Normal text (<18pt) | 4.5:1 | 7:1 |
| Large text (≥18pt or ≥14pt bold) | 3:1 | 4.5:1 |
| UI components and graphical objects | 3:1 | 3:1 |

**Tools:** WebAIM Contrast Checker, Chrome DevTools (inspect → color picker shows ratio), axe DevTools.

---

## 2. Missing Image Alt Text

**WCAG:** 1.1.1 (A) | **Prevalence:** 55% of pages | **Severity:** Critical (functional images) / Low (decorative)

**Before (fails):**
```html
<!-- No alt attribute at all -->
<img src="product-photo.jpg">

<!-- Empty alt on a functional image -->
<img src="search-icon.svg" alt="">
```

**After (passes):**
```html
<!-- Descriptive alt for functional image -->
<img src="product-photo.jpg" alt="Blue wireless headphones, side view">

<!-- Empty alt for decorative image -->
<img src="decorative-swoosh.svg" alt="">

<!-- Functional icon with alt describing action -->
<button>
  <img src="search-icon.svg" alt="Search">
</button>
```

**Alt text decision tree:**

1. Is the image decorative (adds no information)? → `alt=""`
2. Is it a functional image (link, button)? → Describe the action/destination
3. Is it informational? → Describe the content
4. Is it complex (chart, diagram)? → Brief alt + longer description nearby or on linked page
5. Is it an image of text? → Alt text = the text in the image

**Common mistakes:**
- `alt="image"` or `alt="photo"` — tells the user nothing
- `alt="IMG_2847.jpg"` — filename as alt
- Long alt text on decorative images — adds noise for screen reader users
- Missing alt on linked images — link becomes "unlabeled" for screen readers

---

## 3. Missing Form Labels

**WCAG:** 1.1.1, 1.3.1 (A) | **Prevalence:** 46% of pages | **Severity:** Critical

Screen reader users hear "edit text" with no indication of what to type.

**Before (fails):**
```html
<!-- Placeholder is not a label -->
<input type="email" placeholder="Enter your email">

<!-- Label not programmatically associated -->
<span>Email</span>
<input type="email">

<!-- Wrapping div breaks association -->
<label>Email</label>
<div>
  <input type="email">
</div>
```

**After (passes):**
```html
<!-- Explicit label with for/id -->
<label for="email">Email address</label>
<input type="email" id="email" autocomplete="email">

<!-- Implicit label (wrapping) -->
<label>
  Email address
  <input type="email" autocomplete="email">
</label>

<!-- Visually hidden label when design doesn't allow visible label -->
<label for="search" class="visually-hidden">Search</label>
<input type="search" id="search" placeholder="Search...">
```

**The visually-hidden class** (use this instead of `display: none` or `visibility: hidden`, which hide from screen readers too):
```css
.visually-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}
```

---

## 4. Empty Links

**WCAG:** 2.4.4 (A) | **Prevalence:** 44% of pages | **Severity:** High

Links with no text are announced as "link" with no destination — useless for screen reader users.

**Before (fails):**
```html
<!-- Icon-only link with no accessible name -->
<a href="/settings">
  <i class="icon-gear"></i>
</a>

<!-- Image link with no alt -->
<a href="/home">
  <img src="logo.png">
</a>
```

**After (passes):**
```html
<!-- aria-label provides the accessible name -->
<a href="/settings" aria-label="Settings">
  <i class="icon-gear" aria-hidden="true"></i>
</a>

<!-- Visually hidden text -->
<a href="/settings">
  <i class="icon-gear" aria-hidden="true"></i>
  <span class="visually-hidden">Settings</span>
</a>

<!-- Image link with descriptive alt -->
<a href="/home">
  <img src="logo.png" alt="Acme Co — Home">
</a>
```

---

## 5. Empty Buttons

**WCAG:** 2.4.4 (A) | **Prevalence:** 27% of pages | **Severity:** High

Same problem as empty links — buttons with no text are announced as "button" with no purpose.

**Before (fails):**
```html
<!-- Icon button with no accessible name -->
<button>
  <svg><!-- close icon --></svg>
</button>

<!-- Value-less button -->
<button type="submit"></button>
```

**After (passes):**
```html
<!-- aria-label on button -->
<button aria-label="Close dialog">
  <svg aria-hidden="true"><!-- close icon --></svg>
</button>

<!-- Visible text is always best -->
<button type="submit">Submit application</button>
```

---

## 6. Missing Document Language

**WCAG:** 3.1.1 (A) | **Prevalence:** 18% of pages | **Severity:** Moderate

Without `lang`, screen readers may use wrong pronunciation rules for the entire page.

**Before (fails):**
```html
<html>
```

**After (passes):**
```html
<html lang="en">

<!-- For inline language changes (3.1.2 — AA) -->
<p>The French word <span lang="fr">bonjour</span> means hello.</p>
```

---

## 7. Missing Skip Navigation

**WCAG:** 2.4.1 (A) | **Severity:** High

Keyboard users must Tab through the entire navigation on every page without a skip link.

**Before (fails):**
```html
<body>
  <nav><!-- 20+ navigation links --></nav>
  <main><!-- content --></main>
</body>
```

**After (passes):**
```html
<body>
  <a href="#main-content" class="skip-link">Skip to main content</a>
  <nav><!-- navigation --></nav>
  <main id="main-content"><!-- content --></main>
</body>
```

```css
.skip-link {
  position: absolute;
  top: -40px;
  left: 0;
  padding: 8px 16px;
  background: #000;
  color: #fff;
  z-index: 100;
  transition: top 0.2s;
}

.skip-link:focus {
  top: 0;
}
```

---

## 8. No Visible Focus Indicator

**WCAG:** 2.4.7 (AA) | **Severity:** High

Keyboard users lose track of where they are on the page.

**Before (fails):**
```css
/* Common CSS reset that kills accessibility */
*:focus {
  outline: none;
}

/* Or more targeted but still bad */
button:focus,
a:focus {
  outline: none;
}
```

**After (passes):**
```css
/* Custom focus style that's visible and attractive */
:focus-visible {
  outline: 2px solid #1a73e8;
  outline-offset: 2px;
  border-radius: 2px;
}

/* Remove focus ring for mouse clicks, keep for keyboard */
:focus:not(:focus-visible) {
  outline: none;
}
```

**Focus indicator requirements (2.4.13 — AAA):**
- At least 2px thick perimeter
- At least 3:1 contrast between focused and unfocused states
- Area: (width × 4) + (height × 4) minimum pixels of change

---

## 9. Incorrect Heading Hierarchy

**WCAG:** 1.3.1 (A) | **Severity:** Moderate

Screen reader users navigate by headings. Skipped levels create confusion.

**Before (fails):**
```html
<h1>Product Page</h1>
<h3>Features</h3>        <!-- Skipped h2 -->
<h5>Pricing</h5>          <!-- Skipped h4 -->
<h2>Reviews</h2>          <!-- Back to h2 — confusing -->
```

**After (passes):**
```html
<h1>Product Page</h1>
  <h2>Features</h2>
    <h3>Core Features</h3>
    <h3>Advanced Features</h3>
  <h2>Pricing</h2>
  <h2>Reviews</h2>
```

**Rules:**
- One `<h1>` per page
- Never skip levels going down (h1 → h3)
- Can skip levels going back up (h3 → h2 is fine)
- Use headings for structure, not for styling (use CSS for visual size)

---

## 10. Inaccessible Custom Components

**WCAG:** 4.1.2 (A) | **Severity:** Critical

Custom dropdowns, modals, tabs, and toggles that don't expose role, state, or keyboard support.

**Before (fails) — Custom dropdown:**
```html
<div class="dropdown" onclick="toggle()">
  <div class="selected">Choose an option</div>
  <div class="options" style="display:none">
    <div onclick="select('a')">Option A</div>
    <div onclick="select('b')">Option B</div>
  </div>
</div>
```

**After (passes) — Use native HTML first:**
```html
<label for="options">Choose an option</label>
<select id="options">
  <option value="a">Option A</option>
  <option value="b">Option B</option>
</select>
```

**If custom is required — ARIA combobox pattern:**
```html
<label id="combo-label">Choose an option</label>
<div role="combobox"
     aria-expanded="false"
     aria-haspopup="listbox"
     aria-labelledby="combo-label"
     tabindex="0">
  <span>Choose an option</span>
</div>
<ul role="listbox" aria-labelledby="combo-label" hidden>
  <li role="option" id="opt-a">Option A</li>
  <li role="option" id="opt-b">Option B</li>
</ul>
```

---

## 11. Inaccessible Modal Dialogs

**WCAG:** 2.1.2, 2.4.3, 4.1.2 (A) | **Severity:** Critical

Modals that don't trap focus, don't return focus, or aren't announced.

**After (passes):**
```html
<div role="dialog"
     aria-modal="true"
     aria-labelledby="dialog-title"
     tabindex="-1">
  <h2 id="dialog-title">Confirm deletion</h2>
  <p>Are you sure you want to delete this item?</p>
  <button>Cancel</button>
  <button>Delete</button>
</div>
```

**Required behaviors:**
1. Move focus to dialog (or first focusable element) on open
2. Trap Tab cycling within the dialog
3. Close on Escape
4. Return focus to the trigger element on close
5. Make content behind dialog inert (`aria-hidden="true"` on the rest of the page, or use `<dialog>` element)

---

## 12. Missing Status Messages

**WCAG:** 4.1.3 (AA) | **Severity:** High

Success messages, error counts, search results — if focus doesn't move there, screen readers don't know about them.

**Before (fails):**
```html
<!-- Visually appears but screen reader doesn't announce it -->
<div class="toast success">Item saved successfully!</div>
```

**After (passes):**
```html
<!-- Polite announcement (doesn't interrupt) -->
<div role="status" aria-live="polite">Item saved successfully!</div>

<!-- Assertive announcement (interrupts — use for errors) -->
<div role="alert" aria-live="assertive">
  3 errors found. Please fix the highlighted fields.
</div>

<!-- Live region approach — add region first, then inject content -->
<div aria-live="polite" id="search-status"></div>
<script>
  document.getElementById('search-status').textContent = '42 results found';
</script>
```

---

## 13. Insufficient Touch Target Size

**WCAG:** 2.5.8 (AA, new in 2.2) | **Severity:** Moderate

Small targets cause mis-taps, especially for users with motor impairments.

**Before (fails):**
```css
/* 16×16px icon button */
.icon-btn {
  width: 16px;
  height: 16px;
  padding: 0;
}
```

**After (passes):**
```css
/* Meets AA minimum of 24×24px */
.icon-btn {
  min-width: 24px;
  min-height: 24px;
  padding: 4px; /* visual icon can be smaller, tap target is larger */
}

/* Meets AAA target of 44×44px */
.icon-btn-large {
  min-width: 44px;
  min-height: 44px;
  padding: 10px;
}
```

**Exceptions:** Inline links in text, browser-default controls, targets where size is essential.

---

## 14. Focus Hidden Behind Sticky Elements

**WCAG:** 2.4.11 (AA, new in 2.2) | **Severity:** Moderate

Sticky headers, footers, or cookie banners can obscure the focused element.

**Fix approaches:**
```css
/* Ensure scroll-padding accounts for sticky header */
html {
  scroll-padding-top: 80px; /* height of sticky header */
}

/* Or use scroll-margin on focusable elements */
:focus-visible {
  scroll-margin-top: 80px;
  scroll-margin-bottom: 60px; /* height of sticky footer */
}
```

**Also check:** Cookie consent banners, floating action buttons, chat widgets, notification bars.

---

## 15. Drag Without Alternative

**WCAG:** 2.5.7 (AA, new in 2.2) | **Severity:** Moderate

Drag-and-drop must have non-drag alternatives for users who can't perform dragging movements.

**Before (fails):**
```html
<!-- Only drag-and-drop to reorder -->
<ul class="sortable">
  <li draggable="true">Item 1</li>
  <li draggable="true">Item 2</li>
  <li draggable="true">Item 3</li>
</ul>
```

**After (passes):**
```html
<!-- Drag-and-drop PLUS move buttons -->
<ul class="sortable">
  <li draggable="true">
    Item 1
    <button aria-label="Move Item 1 up" disabled>↑</button>
    <button aria-label="Move Item 1 down">↓</button>
  </li>
  <li draggable="true">
    Item 2
    <button aria-label="Move Item 2 up">↑</button>
    <button aria-label="Move Item 2 down">↓</button>
  </li>
</ul>
```
