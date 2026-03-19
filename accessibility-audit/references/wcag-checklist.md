# WCAG 2.2 Checklist — Organized by Audit Task

This checklist reorganizes WCAG 2.2 success criteria by what you're actually checking during an audit, rather than by WCAG principle number. Each section groups related criteria that you'd test together.

---

## 1. Text Alternatives and Media

Check all non-text content for appropriate alternatives.

### Images (1.1.1 — A)

- [ ] Functional images (convey information) have descriptive `alt` text
- [ ] Decorative images have `alt=""` or are implemented as CSS backgrounds
- [ ] Linked images have `alt` text describing the destination
- [ ] Image buttons have `alt` text describing the action
- [ ] Complex images (charts, infographics) have extended descriptions in context or on a linked page
- [ ] Image map hotspots have appropriate `alt` text
- [ ] Images of text are not used when real text could achieve the same presentation (1.4.5 — AA)

### Audio and Video

| Criterion | Level | Requirement |
|---|---|---|
| 1.2.1 | A | Audio-only: descriptive transcript. Video-only: transcript or audio description |
| 1.2.2 | A | Prerecorded video with audio: synchronized captions |
| 1.2.3 | A | Prerecorded video: transcript or audio description |
| 1.2.4 | AA | Live audio: synchronized captions |
| 1.2.5 | AA | Prerecorded video: audio descriptions |
| 1.2.6 | AAA | Prerecorded video: sign language interpretation |
| 1.2.7 | AAA | Extended audio descriptions when pauses insufficient |
| 1.2.8 | AAA | Prerecorded video: full descriptive transcript |
| 1.2.9 | AAA | Live audio: text transcript (e.g., script) |

### Embedded Content

- [ ] Frames and iframes have descriptive `title` attributes (1.1.1 — A)
- [ ] Embedded multimedia is identified via accessible text (1.1.1 — A)

---

## 2. Semantic Structure and Relationships

Check that content structure is programmatically determinable.

### Headings (1.3.1 — A)

- [ ] Heading levels don't skip (h1 → h2 → h3, never h1 → h3)
- [ ] Page has exactly one `<h1>`
- [ ] Headings describe the content that follows
- [ ] Heading levels reflect content hierarchy, not visual styling
- [ ] Section headings are used to organize long content (2.4.10 — AAA)

### Landmarks and Regions (1.3.1 — A, 1.3.6 — AAA)

- [ ] Page uses semantic landmarks: `<header>`, `<nav>`, `<main>`, `<footer>`, `<aside>`
- [ ] Multiple instances of the same landmark have unique labels (`aria-label`)
- [ ] ARIA landmark roles are used to enhance HTML where needed (1.3.6 — AAA)

### Lists (1.3.1 — A)

- [ ] Related items use `<ul>`, `<ol>`, or `<dl>` — not styled `<div>`s
- [ ] Navigation menus use list markup

### Tables (1.3.1 — A)

- [ ] Data tables use `<th>` for headers with `scope` attribute
- [ ] Complex tables use `id`/`headers` associations
- [ ] Table captions use `<caption>` element
- [ ] Layout tables (if any) do NOT use `<th>`, `<caption>`, or `summary`

### Reading Order (1.3.2 — A)

- [ ] DOM order matches visual order
- [ ] CSS doesn't create a reading order that contradicts the DOM
- [ ] Content makes sense when linearized (single column)

### Sensory Characteristics (1.3.3 — A)

- [ ] Instructions don't rely solely on shape, size, or position ("click the green button on the right")
- [ ] Instructions don't rely solely on sound ("a beep indicates success")

---

## 3. Color and Contrast

### Text Contrast

| Criterion | Level | Requirement |
|---|---|---|
| 1.4.3 | AA | Normal text: ≥ 4.5:1. Large text (18pt+ or 14pt+ bold): ≥ 3:1 |
| 1.4.6 | AAA | Normal text: ≥ 7:1. Large text: ≥ 4.5:1 |

### Non-Text Contrast (1.4.11 — AA)

- [ ] UI components (buttons, inputs, dropdowns): ≥ 3:1 against adjacent colors
- [ ] Graphical objects conveying information (icons, chart segments): ≥ 3:1
- [ ] Focus indicators: ≥ 3:1 against background
- [ ] Component states (hover, active, selected): maintain ≥ 3:1

### Color as Information (1.4.1 — A)

- [ ] Color is not the sole method of conveying information
- [ ] Links are distinguishable from body text by more than color alone (underline, or ≥ 3:1 contrast + hover/focus change)
- [ ] Form errors indicated by more than a red border (add icon, text, or pattern)
- [ ] Charts use patterns or labels in addition to color

---

## 4. Keyboard Access

### Full Keyboard Support (2.1.1 — A)

- [ ] All interactive elements are reachable via `Tab`
- [ ] All interactive elements can be activated via `Enter` or `Space`
- [ ] Custom widgets support expected keyboard patterns (arrows for tabs/menus, Escape to close)
- [ ] No keyboard traps — user can always Tab away (2.1.2 — A)
- [ ] Character key shortcuts can be disabled or remapped (2.1.4 — A)

### Focus Management

| Criterion | Level | Requirement |
|---|---|---|
| 2.4.3 | A | Focus order is logical and intuitive |
| 2.4.7 | AA | Focus indicator is visible on all interactive elements |
| 2.4.11 | AA | Focused element not entirely hidden by other content (2.2) |
| 2.4.12 | AAA | Focused element is fully visible (2.2) |
| 2.4.13 | AAA | Custom focus indicator meets size (2px perimeter) and contrast (3:1) requirements (2.2) |

### Focus Behavior

- [ ] Focus moves to modals when opened
- [ ] Focus is trapped within open modals (can't Tab to content behind)
- [ ] Focus returns to trigger element when modal closes
- [ ] Focus moves to new content when dynamically added (e.g., error summary)
- [ ] Focus is not moved unexpectedly

---

## 5. Pointer and Touch Input

### Pointer Gestures (2.5.1 — A)

- [ ] Multipoint gestures (pinch, swipe) have single-pointer alternatives
- [ ] Path-based gestures (drag) have click/tap alternatives

### Pointer Behavior

| Criterion | Level | Requirement |
|---|---|---|
| 2.5.2 | A | Actions fire on `mouseup`/`touchend`, not `mousedown`/`touchstart` (cancellable) |
| 2.5.3 | A | Accessible name includes the visible text label |
| 2.5.4 | A | Motion-based activation (shake, tilt) has standard control alternative and can be disabled |
| 2.5.7 | AA | Drag operations have non-drag alternatives (2.2) |

### Target Size

| Criterion | Level | Requirement |
|---|---|---|
| 2.5.8 | AA | Targets ≥ 24×24px, or spaced so 24px circles don't overlap (2.2) |
| 2.5.5 | AAA | Targets ≥ 44×44px |

---

## 6. Forms and Input

### Labels and Instructions

- [ ] Every input has a programmatic label: `<label for="...">` or `aria-label` (1.1.1, 1.3.1 — A)
- [ ] Related inputs grouped with `<fieldset>` and `<legend>` (1.3.1 — A)
- [ ] Required fields indicated in the label (not just by color or asterisk alone) (3.3.2 — A)
- [ ] Input purpose identified with `autocomplete` for personal data (1.3.5 — AA)
- [ ] Sufficient instructions and examples provided (3.3.2 — A)

### Error Handling

| Criterion | Level | Requirement |
|---|---|---|
| 3.3.1 | A | Errors identified and described in text |
| 3.3.3 | AA | Suggestions provided for fixing errors |
| 3.3.4 | AA | Legal/financial/test data: submissions reversible, verified, or confirmed |
| 3.3.6 | AAA | All submissions: reversible, verified, or confirmed |

### Error Presentation

- [ ] Error messages identify which field has the error
- [ ] Error messages describe what's wrong and how to fix it
- [ ] Errors are announced to screen readers (via `aria-live`, `aria-describedby`, or focus management)
- [ ] Error summary at top of form links to each problematic field

### New in 2.2

- [ ] Redundant entry: information is auto-populated or selectable — don't ask twice (3.3.7 — A)
- [ ] Authentication: no cognitive function tests without alternatives (3.3.8 — AA)

---

## 7. Navigation and Wayfinding

### Page-Level

- [ ] Skip link to main content (2.4.1 — A)
- [ ] Descriptive page title: "[Page] — [Site]" (2.4.2 — A)
- [ ] `<html lang="...">` set correctly (3.1.1 — A)
- [ ] Language changes within page marked with `lang` attribute (3.1.2 — AA)

### Site-Level

- [ ] Multiple navigation methods: nav + search, or nav + sitemap (2.4.5 — AA)
- [ ] Navigation order consistent across pages (3.2.3 — AA)
- [ ] Same functionality labeled consistently across pages (3.2.4 — AA)
- [ ] Help mechanisms in consistent location (3.2.6 — A, new in 2.2)

### Links

- [ ] Link text describes the destination (not "click here" or "read more") (2.4.4 — A)
- [ ] Links with identical text go to identical destinations (2.4.4 — A)
- [ ] Link text alone is sufficient to determine purpose (2.4.9 — AAA)

---

## 8. Time, Motion, and Interruptions

### Time Limits (2.2.1 — A)

- [ ] Users can extend, adjust, or turn off time limits
- [ ] Users warned before timeout that could lose data (2.2.6 — AAA)
- [ ] Re-authentication preserves user data (2.2.5 — AAA)

### Motion and Animation

- [ ] Auto-playing content (carousels, animations) can be paused/stopped after 5 seconds (2.2.2 — A)
- [ ] No content flashes more than 3 times per second (2.3.1 — A)
- [ ] `prefers-reduced-motion` media query respected (2.3.3 — AAA)
- [ ] Auto-updating content (feeds, tickers) can be paused (2.2.2 — A)

### Audio

- [ ] Auto-playing audio (>3 seconds) can be paused, stopped, or volume adjusted (1.4.2 — A)

---

## 9. Text and Content Presentation

### Resizing and Reflow

| Criterion | Level | Requirement |
|---|---|---|
| 1.4.4 | AA | Content readable and functional at 200% zoom |
| 1.4.10 | AA | No horizontal scroll at 320px width (400% zoom) — responsive design |
| 1.4.12 | AA | No content loss when text spacing increased (line-height 1.5×, paragraph 2×, word 0.16×, letter 0.12×) |

### Text Presentation (1.4.8 — AAA)

- [ ] Line length ≤ 80 characters
- [ ] Text not fully justified (no left + right alignment)
- [ ] Line spacing ≥ 1.5× font size
- [ ] Paragraph spacing ≥ 1.5× line spacing
- [ ] Foreground and background colors are defined/inheritable

### Readability

- [ ] Content written at appropriate reading level (3.1.5 — AAA: ~9th grade)
- [ ] Unusual words defined (3.1.3 — AAA)
- [ ] Abbreviations expanded on first use (3.1.4 — AAA)

---

## 10. Predictability and Behavior

### No Surprise Changes

- [ ] Receiving focus doesn't trigger page changes (3.2.1 — A)
- [ ] Changing an input value doesn't trigger unexpected changes (3.2.2 — A)
- [ ] Major changes only happen on user request (3.2.5 — AAA)

### Hover and Focus Content (1.4.13 — AA)

- [ ] Content appearing on hover/focus is dismissible (Esc key)
- [ ] User can hover over the new content without it disappearing
- [ ] Content persists until focus moves, user dismisses it, or it's no longer relevant

---

## 11. ARIA and Custom Components (4.1.2 — A)

### General ARIA Rules

1. Don't use ARIA if native HTML works
2. Don't change native semantics unless necessary
3. All interactive ARIA controls must be keyboard operable
4. Don't use `role="presentation"` or `aria-hidden="true"` on focusable elements
5. All interactive elements must have accessible names

### Common ARIA Patterns

| Component | Required ARIA | Key Behaviors |
|---|---|---|
| Modal/Dialog | `role="dialog"`, `aria-modal="true"`, `aria-labelledby` | Focus trap, Esc to close, return focus |
| Tab Panel | `role="tablist"`, `role="tab"`, `role="tabpanel"`, `aria-selected` | Arrow keys between tabs, Tab into panel |
| Accordion | `aria-expanded`, `aria-controls` | Enter/Space to toggle, optional arrow keys |
| Menu | `role="menu"`, `role="menuitem"`, `aria-haspopup` | Arrow keys to navigate, Esc to close |
| Alert | `role="alert"` or `aria-live="assertive"` | Auto-announced by screen readers |
| Status | `role="status"` or `aria-live="polite"` | Announced at next pause |
| Toggle | `aria-pressed="true/false"` | Space/Enter to toggle, state announced |
| Combobox | `role="combobox"`, `aria-expanded`, `aria-activedescendant` | Type to filter, arrows to select |

### Status Messages (4.1.3 — AA)

- [ ] Success messages announced via `aria-live="polite"` or `role="status"`
- [ ] Error messages announced via `aria-live="assertive"` or `role="alert"`
- [ ] Loading states announced (e.g., `aria-busy="true"` on region, or live region update)
- [ ] Search result counts announced
