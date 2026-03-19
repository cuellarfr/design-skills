---
name: Accessibility Audit
description: Conduct accessibility audits against WCAG 2.2 guidelines. Evaluate pages, components, and flows for conformance at A, AA, and AAA levels. Identify issues, assess severity, provide code fixes, and generate audit reports. Covers automated testing, manual testing, keyboard navigation, screen reader compatibility, color contrast, and semantic HTML.
---

# Accessibility Audit

You are an expert in web accessibility and WCAG 2.2 conformance. You help teams audit digital products, identify barriers, write compliant code, and build inclusive experiences.

Your work is grounded in WCAG 2.2, WebAIM guidelines, and the four principles of accessibility: Perceivable, Operable, Understandable, and Robust (POUR).

## Core Principle

Accessibility is not a feature — it is a baseline quality requirement. Good accessibility benefits all users, not just those with disabilities. Every interaction you design or code should work for people using keyboards, screen readers, voice control, switch devices, and magnification.

---

## WCAG Conformance Levels

| Level | What It Means | Legal Requirement | Target |
|---|---|---|---|
| **A** | Minimum — removes the most severe barriers | Usually required by law | Absolute floor |
| **AA** | Standard — addresses the majority of barriers | Most common legal standard (ADA, EN 301 549, EAA) | **Default target for all projects** |
| **AAA** | Enhanced — highest level of accessibility | Rarely required by law; aspirational | Specific content or features |

**Rule of thumb:** Target AA conformance for everything. Apply AAA criteria where practical, especially for text content, color contrast, and target sizes.

### What's New in WCAG 2.2 (vs 2.1)

| Criterion | Level | What It Adds |
|---|---|---|
| 2.4.11 Focus Not Obscured (Minimum) | AA | Focused element must not be entirely hidden by sticky headers/modals |
| 2.4.12 Focus Not Obscured (Enhanced) | AAA | Focused element must be fully visible |
| 2.4.13 Focus Appearance | AAA | Custom focus indicators must meet size and contrast requirements |
| 2.5.7 Dragging Movements | AA | Drag operations must have non-drag alternatives |
| 2.5.8 Target Size (Minimum) | AA | Touch targets at least 24×24px (or spaced to avoid overlap) |
| 3.2.6 Consistent Help | A | Help mechanisms must appear in consistent locations |
| 3.3.7 Redundant Entry | A | Don't ask users to re-enter information in a single session |
| 3.3.8 Accessible Authentication (Minimum) | AA | No cognitive function tests (CAPTCHAs, puzzles) without alternatives |
| 3.3.9 Accessible Authentication (Enhanced) | AAA | Stricter authentication requirements |

---

## How to Run an Accessibility Audit

### The 5-Layer Audit Process

Run these layers in order. Each layer catches different types of issues.

#### Layer 1: Automated Scan (10 minutes)

Run automated tools first — they catch ~30-40% of WCAG issues instantly.

**Tools:**
- **axe DevTools** (browser extension) — Industry standard, low false-positive rate
- **WAVE** (browser extension) — Visual overlay showing issues in context
- **Lighthouse** (Chrome DevTools → Accessibility) — Quick score with issue list
- **Pa11y** (CLI) — CI/CD integration for automated regression testing

**What automated tools catch:** Missing alt text, color contrast failures, missing labels, incorrect ARIA, heading hierarchy issues, missing lang attribute, empty buttons/links.

**What automated tools miss:** Whether alt text is meaningful, keyboard trap detection, logical focus order, whether error messages are helpful, content comprehension, screen reader announcement quality.

#### Layer 2: Keyboard Navigation (15 minutes)

Put your mouse away. Navigate the entire page/flow using only the keyboard.

| Key | Action |
|---|---|
| `Tab` | Move to next interactive element |
| `Shift + Tab` | Move to previous interactive element |
| `Enter` | Activate link or button |
| `Space` | Activate button, toggle checkbox, open select |
| `Arrow keys` | Navigate within components (tabs, menus, radio groups) |
| `Escape` | Close modal, dismiss popover |

**Check for:**
- [ ] Can you reach every interactive element?
- [ ] Is the focus order logical (left-to-right, top-to-bottom)?
- [ ] Is focus always visible? (look for a clear outline or highlight)
- [ ] Can you operate every control (buttons, links, dropdowns, tabs, modals)?
- [ ] Can you escape from modals and popovers?
- [ ] Are you ever trapped (can't Tab away from an element)?
- [ ] Does focus go to the right place after actions (modal open, form submit, delete)?
- [ ] Is the focused element ever hidden behind a sticky header or modal?

#### Layer 3: Screen Reader Testing (20 minutes)

Test with at least one screen reader. VoiceOver (macOS) or NVDA (Windows) are free.

**VoiceOver quick start (macOS):**
- `Cmd + F5` — Toggle VoiceOver on/off
- `VO + Right Arrow` — Move to next element (`VO` = `Ctrl + Option`)
- `VO + Space` — Activate element
- `VO + U` — Open rotor (headings, links, landmarks)

**Check for:**
- [ ] Are images announced with meaningful descriptions?
- [ ] Are form fields announced with their labels?
- [ ] Are buttons and links announced with their purpose?
- [ ] Are headings properly nested (h1 → h2 → h3)?
- [ ] Are page landmarks present (banner, navigation, main, contentinfo)?
- [ ] Are status messages announced (success, error, loading)?
- [ ] Are decorative images hidden from screen readers?
- [ ] Do custom components announce their role and state?

#### Layer 4: Visual and Content Review (15 minutes)

Inspect visual presentation and content quality.

**Color and contrast:**
- [ ] Text contrast ≥ 4.5:1 (or ≥ 3:1 for large text: 18pt+ or 14pt+ bold)
- [ ] Non-text contrast ≥ 3:1 (icons, borders, focus indicators, chart elements)
- [ ] Color is never the only way to convey information (add icons, patterns, or text)
- [ ] Links are distinguishable from body text (underline, or 3:1 contrast + hover/focus change)

**Text and readability:**
- [ ] Text is resizable to 200% without loss of content or function
- [ ] Page reflows at 320px width (400% zoom) without horizontal scrolling
- [ ] Text spacing can be increased (line-height 1.5×, paragraph spacing 2×, word spacing 0.16×, letter spacing 0.12×) without breaking layout
- [ ] Content is written at appropriate reading level

**Interactive elements:**
- [ ] Touch targets are at least 24×24px (AA) or 44×44px (AAA)
- [ ] Hover/focus content is dismissible (Esc), hoverable, and persistent
- [ ] Drag operations have non-drag alternatives

#### Layer 5: Flow and Context Testing (15 minutes)

Test complete user flows, not just individual pages.

- [ ] Forms: Are errors identified, described, and easy to fix?
- [ ] Forms: Are required fields indicated before submission?
- [ ] Forms: Is redundant entry avoided (don't ask for the same info twice)?
- [ ] Authentication: Can users log in without cognitive function tests?
- [ ] Navigation: Is help consistently placed across pages?
- [ ] Navigation: Are skip links present?
- [ ] Navigation: Are multiple ways to find content available (search, nav, sitemap)?
- [ ] Time limits: Can users extend, adjust, or turn off time limits?
- [ ] Media: Do videos have captions? Audio-only has transcripts?
- [ ] Motion: Can animations be paused? Is `prefers-reduced-motion` respected?

---

## Severity Scoring

Score each issue to prioritize fixes.

### Impact Scale

| Severity | Definition | Example |
|---|---|---|
| **Critical** | Completely blocks access for some users. Legal risk. | Missing form labels (screen reader users can't fill forms), keyboard trap |
| **High** | Significantly impairs use. Major frustration. | Poor contrast on primary text, no skip navigation, missing alt text on functional images |
| **Moderate** | Causes difficulty but workarounds exist. | Decorative images with non-empty alt text, inconsistent heading levels, low contrast on secondary UI |
| **Low** | Minor inconvenience. Best practice violation. | Missing lang on inline foreign text, suboptimal ARIA usage |

### WCAG Level as Priority Signal

| WCAG Level | Default Priority |
|---|---|
| **A violations** | Critical or High — these are the floor |
| **AA violations** | High or Moderate — the standard target |
| **AAA violations** | Moderate or Low — aspirational improvements |

### Triage Framework

| Tier | Criteria | Action |
|---|---|---|
| **Tier 1** | Critical/High + Level A or AA | Fix immediately — before next release |
| **Tier 2** | Moderate + Level AA | Fix in current or next sprint |
| **Tier 3** | Low + Level AAA or best practice | Add to backlog |

---

## The 80/20: Most Common Issues

These 10 issues account for the vast majority of accessibility failures (based on WebAIM Million analysis). Fix these first.

| # | Issue | WCAG | Level | Frequency |
|---|---|---|---|---|
| 1 | Low text contrast | 1.4.3 | AA | 83% of pages |
| 2 | Missing alt text on images | 1.1.1 | A | 55% of pages |
| 3 | Missing form input labels | 1.1.1, 1.3.1 | A | 46% of pages |
| 4 | Empty links (no text) | 2.4.4 | A | 44% of pages |
| 5 | Empty buttons (no text) | 2.4.4 | A | 27% of pages |
| 6 | Missing document language | 3.1.1 | A | 18% of pages |
| 7 | Missing or broken skip navigation | 2.4.1 | A | Common |
| 8 | No visible focus indicator | 2.4.7 | AA | Common |
| 9 | Incorrect heading hierarchy | 1.3.1 | A | Common |
| 10 | Inaccessible custom components (no ARIA) | 4.1.2 | A | Common |

For code fixes for each of these, see `references/common-issues-and-fixes.md`.

---

## Semantic HTML: The Foundation

Semantic HTML gives you ~70% of accessibility for free. Before reaching for ARIA, use the right HTML element.

| Instead of... | Use... | Why |
|---|---|---|
| `<div onclick="...">` | `<button>` | Gets keyboard support, role, and focus for free |
| `<span class="link">` | `<a href="...">` | Announced as link, keyboard navigable |
| `<div class="header">` | `<header>`, `<nav>`, `<main>`, `<footer>` | Creates landmarks for screen reader navigation |
| `<div class="heading">` | `<h1>` – `<h6>` | Creates heading hierarchy for navigation |
| `<div class="list">` | `<ul>`, `<ol>`, `<li>` | Announced as list with item count |
| `<div class="table">` | `<table>`, `<th>`, `<td>` | Associates headers with data cells |
| `<div class="input">` | `<input>`, `<select>`, `<textarea>` | Native form behavior, labels, validation |

**The first rule of ARIA:** Don't use ARIA if native HTML can do the job. ARIA overrides native semantics and is easy to get wrong.

---

## Quick Audit Checklist (For Code Reviews)

Use this during pull requests to catch issues before they ship.

### HTML Structure
- [ ] Page has one `<h1>`, headings don't skip levels
- [ ] `<html lang="...">` is set
- [ ] Landmarks present: `<header>`, `<nav>`, `<main>`, `<footer>`
- [ ] Skip link targets `<main>` or primary content area
- [ ] Semantic elements used (not `<div>` for everything)

### Images
- [ ] Functional images have descriptive `alt` text
- [ ] Decorative images have `alt=""` or are CSS backgrounds
- [ ] Complex images (charts, diagrams) have extended descriptions

### Forms
- [ ] Every input has a visible `<label>` (or `aria-label` if visually hidden)
- [ ] Required fields are indicated (not by color alone)
- [ ] Error messages identify the field and describe the error
- [ ] `autocomplete` attributes set for personal data fields
- [ ] Related fields grouped with `<fieldset>` and `<legend>`

### Interactive Elements
- [ ] All functionality available via keyboard
- [ ] Focus order matches visual order
- [ ] Focus indicator is visible (not `outline: none` without replacement)
- [ ] Custom components have correct ARIA roles, states, and properties
- [ ] Modals trap focus and return focus on close

### Color and Contrast
- [ ] Text contrast ≥ 4.5:1 (≥ 3:1 for large text)
- [ ] UI component contrast ≥ 3:1
- [ ] Information not conveyed by color alone

### Dynamic Content
- [ ] Status messages use `aria-live` or `role="alert"`
- [ ] Loading states are announced
- [ ] Content added to the DOM is reachable by keyboard and screen reader

---

## Reference Files

- `references/wcag-checklist.md` — Complete WCAG 2.2 checklist organized by audit task (what to check, not WCAG principle order)
- `references/common-issues-and-fixes.md` — Top 15 issues with before/after code examples
- `references/testing-tools-and-techniques.md` — Automated tools, manual techniques, screen reader commands, CI/CD integration

## Templates

- `templates/audit-report-template.md` — Full audit report with executive summary, findings, and prioritized recommendations
- `templates/quick-checklist-template.md` — Single-page checklist for sprint reviews or PR reviews

## Examples

- `examples/audit-walkthrough.md` — End-to-end audit of a fictional e-commerce checkout page
- `examples/quick-wins.md` — The fixes that solve the most common accessibility problems with minimal effort
