# Accessibility Quick Checklist

**Page/Component:** [What you're checking]
**Date:** [Date]
**Checker:** [Name]

Use this during sprint reviews, PR reviews, or quick spot-checks. Each item maps to a WCAG criterion.

---

## Structure and Semantics

- [ ] Page has `<html lang="...">` — (3.1.1 A)
- [ ] Page has one `<h1>`, headings don't skip levels — (1.3.1 A)
- [ ] Landmarks present: `<header>`, `<nav>`, `<main>`, `<footer>` — (1.3.1 A)
- [ ] Skip link present and functional — (2.4.1 A)
- [ ] Page has descriptive `<title>` — (2.4.2 A)
- [ ] Lists use `<ul>`/`<ol>`, not styled `<div>`s — (1.3.1 A)
- [ ] Data tables use `<th>` with `scope` — (1.3.1 A)

## Images

- [ ] Functional images have descriptive `alt` — (1.1.1 A)
- [ ] Decorative images have `alt=""` — (1.1.1 A)
- [ ] Complex images have extended description — (1.1.1 A)

## Forms

- [ ] Every input has a `<label>` — (1.3.1 A)
- [ ] Required fields indicated (not by color alone) — (3.3.2 A)
- [ ] Errors identify the field + describe the fix — (3.3.1 A, 3.3.3 AA)
- [ ] `autocomplete` on personal data fields — (1.3.5 AA)
- [ ] No redundant entry in single-session flows — (3.3.7 A)

## Keyboard

- [ ] All interactive elements reachable via Tab — (2.1.1 A)
- [ ] Focus indicator visible on all elements — (2.4.7 AA)
- [ ] Focus order matches visual order — (2.4.3 A)
- [ ] No keyboard traps — (2.1.2 A)
- [ ] Modals trap focus, close on Esc, return focus — (2.1.2 A, 4.1.2 A)
- [ ] Focused elements not hidden behind sticky content — (2.4.11 AA)

## Color and Contrast

- [ ] Text contrast ≥ 4.5:1 (≥ 3:1 large text) — (1.4.3 AA)
- [ ] UI component contrast ≥ 3:1 — (1.4.11 AA)
- [ ] Color not sole method of conveying info — (1.4.1 A)

## Interactive Elements

- [ ] Links have descriptive text (not "click here") — (2.4.4 A)
- [ ] Buttons have accessible names — (4.1.2 A)
- [ ] Touch targets ≥ 24×24px — (2.5.8 AA)
- [ ] Drag operations have non-drag alternatives — (2.5.7 AA)
- [ ] Custom components have correct ARIA — (4.1.2 A)

## Dynamic Content

- [ ] Status messages announced via `aria-live` — (4.1.3 AA)
- [ ] Loading states communicated — (4.1.3 AA)
- [ ] Hover/focus content dismissible + hoverable — (1.4.13 AA)

## Responsive and Visual

- [ ] Content readable at 200% zoom — (1.4.4 AA)
- [ ] No horizontal scroll at 320px width — (1.4.10 AA)
- [ ] Layout survives text spacing changes — (1.4.12 AA)

## Media

- [ ] Videos have captions — (1.2.2 A)
- [ ] Audio-only has transcript — (1.2.1 A)
- [ ] Auto-playing media can be paused — (1.4.2 A)
- [ ] No content flashes > 3 times/second — (2.3.1 A)

## Authentication (2.2)

- [ ] No CAPTCHAs or puzzles without alternatives — (3.3.8 AA)
- [ ] Help in consistent location across pages — (3.2.6 A)

---

## Results

**Issues found:** [#]
**Critical/High:** [List]
**Action items:** [What needs to happen next]
