# Accessibility Testing Tools and Techniques

## Automated Testing Tools

Automated tools catch ~30-40% of WCAG issues. They're fast and essential, but never sufficient alone.

### Browser Extensions

| Tool | Strengths | Limitations | Best For |
|---|---|---|---|
| **axe DevTools** | Low false-positive rate, detailed remediation guidance, WCAG reference links | Doesn't test keyboard or screen reader behavior | Developer daily use, CI/CD |
| **WAVE** | Visual overlay shows issues in context, shows document structure | Can be noisy on complex pages | Quick visual scan, stakeholder demos |
| **Lighthouse** (Chrome) | Built into DevTools, scores 0-100, tracks over time | Less detailed than axe, limited criteria | Quick health check |
| **Accessibility Insights** (Microsoft) | Guided manual testing flow, FastPass + full assessment | Windows/Edge focused | Structured audit process |

### CLI and CI/CD Tools

| Tool | Integration | Use Case |
|---|---|---|
| **axe-core** (npm) | Jest, Cypress, Playwright, Storybook | Unit/integration/E2E test suites |
| **Pa11y** | CLI, CI/CD, dashboard | Automated regression testing |
| **Lighthouse CI** | GitHub Actions, CI pipelines | Performance + accessibility scoring |

### Color Contrast Tools

| Tool | Use Case |
|---|---|
| **WebAIM Contrast Checker** | Check specific color pairs |
| **Chrome DevTools color picker** | Shows contrast ratio inline while inspecting |
| **Stark** (Figma plugin) | Check contrast during design phase |
| **Who Can Use** | Shows how colors appear to users with different vision types |

### Automated Testing Integration Example

```javascript
// axe-core with Playwright
import { test, expect } from '@playwright/test';
import AxeBuilder from '@axe-core/playwright';

test('homepage has no critical accessibility issues', async ({ page }) => {
  await page.goto('/');
  const results = await new AxeBuilder({ page })
    .withTags(['wcag2a', 'wcag2aa', 'wcag22aa'])
    .analyze();
  expect(results.violations).toEqual([]);
});
```

```javascript
// axe-core with Jest and jsdom
import { axe, toHaveNoViolations } from 'jest-axe';

expect.extend(toHaveNoViolations);

test('renders accessible form', async () => {
  const { container } = render(<LoginForm />);
  const results = await axe(container);
  expect(results).toHaveNoViolations();
});
```

---

## Keyboard Testing

### Setup

1. In macOS System Settings → Keyboard, ensure "Keyboard navigation" is on (formerly "Full Keyboard Access")
2. In browser, disable any mouse-tracking extensions
3. Put your mouse out of reach

### Test Script

| Step | Action | Check |
|---|---|---|
| 1 | Press `Tab` repeatedly from the top of the page | Can you reach every interactive element? Is the order logical? |
| 2 | Watch for the focus indicator | Is it always visible? Does it have sufficient contrast? |
| 3 | Press `Enter` on each link | Does it navigate correctly? |
| 4 | Press `Enter` and `Space` on each button | Does it activate? |
| 5 | Navigate to a dropdown/select | Can you open it and select an option with arrow keys? |
| 6 | Navigate to a modal trigger and activate it | Does focus move into the modal? |
| 7 | Inside the modal, press `Tab` repeatedly | Is focus trapped within the modal? |
| 8 | Press `Escape` | Does the modal close? Does focus return to the trigger? |
| 9 | Navigate to a tab component | Can you switch tabs with arrow keys? Tab into the panel? |
| 10 | Fill out and submit a form | Can you complete the entire form with keyboard? |
| 11 | If errors appear, can you navigate to each error? | Does focus move to the error summary or first error? |
| 12 | Check for keyboard traps | Can you always Tab away from every element? |

### Common Keyboard Failures

| Symptom | Likely Cause | Fix |
|---|---|---|
| Can't reach element via Tab | Element is `<div>` or `<span>` without `tabindex="0"` | Use `<button>` or `<a>`, or add `tabindex="0"` with keyboard event handlers |
| Focus disappears | Focus moved to invisible or off-screen element | Check DOM order, check for `display:none` or `visibility:hidden` on focused elements |
| Focus trapped in component | No Escape handler, or Tab not cycling correctly | Add keyboard event listeners for Escape and Tab |
| Custom component doesn't respond to keyboard | Only `onclick` handler, no `onkeydown` | Add `onkeydown` for Enter and Space, or use `<button>` |
| Focus order doesn't match visual order | CSS reordering (flexbox `order`, grid, `position: absolute`) | Align DOM order with visual order |

---

## Screen Reader Testing

### VoiceOver (macOS) — Free

**Essential commands:**

| Action | Keys |
|---|---|
| Toggle VoiceOver on/off | `Cmd + F5` |
| Move to next element | `VO + Right Arrow` (VO = `Ctrl + Option`) |
| Move to previous element | `VO + Left Arrow` |
| Activate element | `VO + Space` |
| Read current element | `VO + F3` |
| Open Rotor | `VO + U` |
| Navigate headings | Rotor → Headings, then Up/Down arrows |
| Navigate landmarks | Rotor → Landmarks, then Up/Down arrows |
| Navigate links | Rotor → Links, then Up/Down arrows |
| Navigate form controls | Rotor → Form Controls, then Up/Down arrows |
| Start continuous reading | `VO + A` |
| Stop reading | `Ctrl` |

**Quick testing flow:**
1. Turn on VoiceOver (`Cmd + F5`)
2. Open the Rotor (`VO + U`), check headings list — are they logical?
3. Check landmarks list — does the page have banner, navigation, main, contentinfo?
4. Navigate through the page with `VO + Right Arrow`
5. On images: does VoiceOver read a useful description?
6. On form fields: does VoiceOver announce the label?
7. On buttons/links: does VoiceOver announce the purpose?
8. Submit a form with errors: does VoiceOver announce the errors?
9. Open a modal: does VoiceOver announce the dialog title?

### NVDA (Windows) — Free

**Essential commands:**

| Action | Keys |
|---|---|
| Toggle NVDA | `Ctrl + Alt + N` |
| Move to next element | `Down Arrow` (browse mode) |
| Move to previous element | `Up Arrow` |
| Activate element | `Enter` |
| Tab to next interactive | `Tab` |
| List headings | `NVDA + F7` → Headings |
| List landmarks | `NVDA + F7` → Landmarks |
| Next heading | `H` |
| Next landmark | `D` |
| Next form field | `F` |
| Next button | `B` |
| Next link | `K` (unvisited) or `V` (visited) |
| Switch browse/focus mode | `NVDA + Space` |

### What to Listen For

| Element | Should Announce | Red Flag |
|---|---|---|
| Image | Role + alt text: "Image: Blue headphones" | "Image" (no description) or "IMG_2847.jpg" |
| Link | "Link: Settings" | "Link" (no text) |
| Button | "Button: Submit form" | "Button" (no text) |
| Form field | "Email, edit text" or "Email, required, edit text" | "Edit text" (no label) |
| Heading | "Heading level 2: Features" | No heading announcement |
| Checkbox | "Accept terms, checkbox, not checked" | "Checkbox" (no label) |
| Error | "Error: Email is required" (via alert or live region) | No announcement |
| Modal | "Dialog: Confirm deletion" | No announcement of dialog |

---

## Manual Visual Testing

### Color Contrast Testing

1. **Inspect element** in DevTools → click color swatch → see contrast ratio
2. **Use WAVE** extension → contrast errors highlighted in red
3. **Grayscale test:** Apply `filter: grayscale(100%)` to `<html>` in DevTools — can you still distinguish all elements?
4. **Color blindness simulation:** Chrome DevTools → Rendering → Emulate vision deficiencies

### Zoom and Reflow Testing

| Test | How | Pass Criteria |
|---|---|---|
| 200% zoom | `Cmd/Ctrl + +` until 200% | Content readable, functional, no overlap |
| 400% zoom / 320px reflow | Set browser to 1280px wide, zoom to 400% | Single column, no horizontal scroll (except tables, maps, toolbars) |
| Text spacing | Use browser extension or bookmarklet to apply: line-height 1.5×, paragraph 2×, word spacing 0.16×, letter spacing 0.12× | No content cut off or overlapping |

### Text Spacing Bookmarklet

Save this as a bookmark and click it on any page to test text spacing compliance (1.4.12):

```javascript
javascript:void(function(){var s=document.createElement('style');s.textContent='*{line-height:1.5em!important;letter-spacing:0.12em!important;word-spacing:0.16em!important}p{margin-bottom:2em!important}';document.head.appendChild(s)})()
```

### Reduced Motion Testing

1. macOS: System Settings → Accessibility → Display → Reduce motion
2. Chrome DevTools: Rendering → Emulate CSS media feature `prefers-reduced-motion: reduce`
3. Check: Do animations stop or simplify? Does the page still work?

---

## Testing Cheat Sheet

### Quick Audit (30 Minutes)

| Time | Layer | What to Do |
|---|---|---|
| 0-10 min | Automated | Run axe DevTools, note all violations |
| 10-20 min | Keyboard | Tab through entire page, check focus visibility and order |
| 20-25 min | Visual | Check contrast (DevTools), zoom to 200%, check color reliance |
| 25-30 min | Screen Reader | VoiceOver/NVDA quick scan: headings, landmarks, form labels, images |

### Full Audit (2-3 Hours Per Page)

| Time | Layer | What to Do |
|---|---|---|
| 0-15 min | Automated | Run axe + WAVE + Lighthouse, compile unique issues |
| 15-35 min | Keyboard | Full keyboard navigation, test all interactive components |
| 35-60 min | Screen Reader | Full page traversal, form completion, error handling, modal interaction |
| 60-80 min | Visual | Contrast check (all states), zoom 200% + 400%, text spacing, reduced motion |
| 80-100 min | Content | Alt text quality, heading structure, link text quality, error message quality |
| 100-120 min | Flow | Complete key user flows (signup, purchase, settings change) with keyboard + screen reader |
| 120-150 min | Documentation | Write findings, assign severity, draft report |

---

## Accessibility Testing in Design Phase

Don't wait until code. Catch issues in design:

| Check | Tool/Method | When |
|---|---|---|
| Color contrast | Stark (Figma), WebAIM Contrast Checker | During visual design |
| Touch target size | Measure in design tool (≥24px AA, ≥44px AAA) | During component design |
| Focus states | Design focus indicators for every interactive element | During interaction design |
| Reading order | Mark intended DOM order in design annotations | During layout design |
| Heading hierarchy | Annotate heading levels on mockups | During content design |
| Alternative text | Write alt text in design annotations for every image | During content design |
| Color as information | Check if removing color breaks understanding | During visual design |
| Error states | Design error messages for every form field | During form design |
