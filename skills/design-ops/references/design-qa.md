# Design QA

Deep reference for verifying implementation matches design specs. Design QA is the last line of defense before users see your work.

---

## Design QA Process

### When to Do Design QA

| Trigger | Scope | Who |
|---------|-------|-----|
| **Per story** | Individual story or component | Assigned designer reviews in staging/Storybook |
| **Per sprint** | All stories completed in the sprint | Design lead reviews sprint deliverables |
| **Pre-release** | Full feature or flow | Designer + QA engineer do a joint review |
| **Post-release** | Production check | Quick spot-check in production environment |

### QA Environment Ladder

Review in this order — catch issues early where they're cheapest to fix:

| Level | Environment | What to Check | When |
|-------|------------|---------------|------|
| 1 | **Storybook / Component sandbox** | Individual component rendering, all states, all variants | During development |
| 2 | **Local development** | Component in context, layout, content, interactions | Before PR merge |
| 3 | **Staging** | Full flow, real data, responsive, cross-browser | After PR merge, before release |
| 4 | **Production** | Final spot-check, real content, real users | After release |

---

## Design QA Checklist (Detailed)

### Visual Accuracy

| Check | How | Pass Criteria |
|-------|-----|--------------|
| **Colors** | Compare hex values using browser dev tools or eyedropper | Match design tokens exactly. No hardcoded hex values |
| **Typography** | Inspect font-family, size, weight, line-height, letter-spacing | Match typography tokens. No visual differences |
| **Spacing** | Inspect margin and padding values | Match spacing tokens. Consistent within the component and page |
| **Border radius** | Inspect border-radius | Match design token. Consistent across similar elements |
| **Shadows** | Inspect box-shadow | Match elevation tokens. Correct layering |
| **Icons** | Visual comparison + inspect SVG | Correct icon, correct size, correct color. SVG (not PNG/JPG) |
| **Images** | Visual comparison + inspect | Correct aspect ratio, no distortion, proper alt text |
| **Alignment** | Overlay comparison or visual inspection | Elements align to grid. No off-by-1px misalignments |

### Interactive States

| State | Check | How to Test |
|-------|-------|------------|
| **Default** | Renders correctly without interaction | Load the page |
| **Hover** | Visual change on mouse hover | Hover over element |
| **Focus** | Visible focus ring on keyboard navigation | Tab to element |
| **Active/Pressed** | Visual change during click/tap | Click and hold |
| **Disabled** | Visually muted, not interactive | Check disabled prop, try to click |
| **Loading** | Spinner, skeleton, or shimmer displays correctly | Throttle network, trigger loading state |
| **Error** | Error state displays with correct message | Trigger error condition |
| **Success** | Success feedback displays correctly | Complete the action successfully |
| **Empty** | Empty state shows appropriate content and CTA | Remove all data |

### Responsive Behavior

| Breakpoint | Viewport | Check |
|-----------|----------|-------|
| **Mobile S** | 320px | Nothing overflows. Content is readable. Touch targets 44px+ |
| **Mobile L** | 414px | Layout accommodates larger phone screens |
| **Tablet** | 768px | Layout transitions correctly (stack → grid, etc.) |
| **Desktop** | 1024px | Full layout renders. No excessive whitespace |
| **Desktop L** | 1440px | Design max-width respected. Content doesn't stretch |
| **Ultra-wide** | 1920px+ | Content stays centered/contained. No layout breaks |

**What to verify at each breakpoint:**
- Elements reflow, stack, or hide as specified
- Typography scales appropriately (or uses responsive tokens)
- Images resize without distortion
- Navigation adapts (hamburger menu, etc.)
- Touch targets remain accessible on touch devices
- No horizontal scrolling

### Content

| Check | What to Look For |
|-------|-----------------|
| **Real content** | No "lorem ipsum" or placeholder text in production |
| **Long strings** | Test with maximum-length content. Truncation works correctly |
| **Short strings** | Test with minimum content. No awkward empty space |
| **Empty states** | Every data-dependent area has an empty state designed |
| **Localization** | If applicable, test with longer languages (German: +30%, Japanese: different character widths) |
| **Pluralization** | "1 item" vs. "2 items" handled correctly |
| **Special characters** | Ampersands, quotes, unicode — no encoding issues |
| **Numbers** | Large numbers formatted correctly (1,234 not 1234). Currencies display properly |

### Interaction and Motion

| Check | How | Pass Criteria |
|-------|-----|--------------|
| **Transitions** | Trigger state changes. Use slow-motion screen recording if needed | Timing matches spec (±50ms). Easing feels right |
| **Animations** | Trigger animated elements | Smooth (60fps). No jank or frame drops |
| **Scroll behavior** | Scroll through the page | Sticky elements work. Scroll-linked animations fire correctly |
| **Drag and drop** | Test drag interactions | Ghost element visible. Drop zones highlighted. Smooth reorder |
| **Gestures (mobile)** | Test on real device | Swipe, pinch, long-press work as specified |
| **Reduced motion** | Toggle `prefers-reduced-motion: reduce` in OS settings | Animations reduced or replaced with instant state changes |

### Accessibility

| Check | Tool | Pass Criteria |
|-------|------|--------------|
| **Automated scan** | axe DevTools, Lighthouse | 0 critical or serious issues |
| **Keyboard navigation** | Tab through the page | All interactive elements reachable. Logical focus order. Focus ring visible |
| **Focus management** | Open/close modals, navigate flows | Focus moves to correct element. Focus trapped in modals. Focus returns on close |
| **Screen reader** | VoiceOver (Mac) or NVDA (Windows) | All content announced. Interactive elements have labels. State changes announced |
| **Color contrast** | Colour Contrast Checker or similar | Text: 4.5:1 minimum (AA). Large text: 3:1. UI components: 3:1 |
| **Touch targets** | Inspect element dimensions | 44×44px minimum hit area |
| **Alt text** | Inspect image elements | All meaningful images have descriptive alt text. Decorative images have `alt=""` |
| **Headings** | Inspect heading hierarchy | Logical order (h1 → h2 → h3). No skipped levels |

### Cross-Browser

| Browser | Priority | Notes |
|---------|----------|-------|
| **Chrome** (latest) | High | Primary development browser. Baseline |
| **Safari** (latest) | High | Different rendering engine (WebKit). CSS differences. Important for Mac/iOS users |
| **Firefox** (latest) | Medium | Gecko engine. Test for layout differences |
| **Edge** (latest) | Medium | Chromium-based, similar to Chrome. Quick check |
| **Mobile Safari** | High | iOS devices. Test on real iPhone if possible |
| **Chrome Android** | High | Android devices. Test on real device if possible |

---

## Filing QA Issues

### Issue Template

```
## [Component/Screen]: [Brief description]

**Severity:** Critical / Major / Minor / Cosmetic
**Environment:** [Browser], [Viewport], [OS]
**Screen:** [Screen name or URL]

### Expected (Design)
[Screenshot from Figma or link to frame]

### Actual (Implementation)
[Screenshot from browser/staging]

### Details
[Specific description of the discrepancy]

### Suggested Fix
[If applicable: specific CSS property, token, or behavior change]
```

### Severity Guidelines

| Severity | Definition | Examples | SLA |
|----------|-----------|----------|-----|
| **Critical** | Functionality broken. User blocked | Button doesn't work. Form can't submit. Page crashes | Fix before release |
| **Major** | Behavior wrong. User confused or misled | Wrong state displayed. Animation breaks layout. Incorrect error message | Fix this sprint |
| **Minor** | Visual discrepancy. Doesn't affect function | Wrong spacing token (16px instead of 24px). Font weight off. Color slightly wrong | Fix next sprint |
| **Cosmetic** | Pixel-level. Only noticed by designers | 1px misalignment. Subtle shadow difference. Animation easing slightly off | Backlog |

### Batch Reporting

For efficiency, group QA issues by screen or component rather than filing individual tickets:

```
## Design QA: Checkout Flow (Sprint 14)

### Payment Screen — 3 issues
1. [Minor] Card icon alignment off by 4px. Expected: centered vertically
2. [Major] Error state missing for declined card. No error message shown
3. [Minor] Input focus ring uses blue instead of design system focus token

### Confirmation Screen — 2 issues
1. [Cosmetic] Order summary spacing is 12px instead of 16px between items
2. [Minor] Success animation doesn't play. Static checkmark only

### Cross-cutting — 1 issue
1. [Major] Tab order skips the "Edit" link on the shipping address section
```

---

## Design QA Metrics

Track these to measure and improve QA effectiveness:

| Metric | Target | How to Measure |
|--------|--------|----------------|
| **First-pass QA rate** | >80% of stories pass on first review | Stories passing QA / total stories |
| **QA issue density** | Decreasing trend | Issues filed per story over time |
| **Critical issues caught** | 0 in production | Critical issues found in QA vs. found in production |
| **Time to fix** | <3 days for Major, <1 sprint for Minor | Days from QA issue filed to fixed |
| **QA coverage** | 100% of stories | Stories with design QA / total stories shipped |
| **Regression rate** | <5% | Previously fixed issues that reappear |

### Preventing QA Issues Upstream

Most QA issues originate earlier in the process:

| QA Issue Root Cause | Upstream Fix |
|--------------------|-------------|
| **Missing states** in implementation | Require all states in handoff spec |
| **Wrong tokens** used | Engineering uses design system + token linting |
| **Layout breaks** at breakpoints | Include responsive specs in handoff |
| **Accessibility gaps** | Add a11y requirements to acceptance criteria |
| **Animation missing or wrong** | Provide motion specs (duration, easing, trigger) |
| **Content overflow** | Test with edge-case content in design |

---

## Automated Design QA

### Visual Regression Testing

Tools that automatically compare screenshots of the UI against reference images:

| Tool | How It Works | Best For |
|------|-------------|----------|
| **Chromatic** | Snapshots every Storybook story. Highlights pixel-level diffs | Component libraries with Storybook |
| **Percy** | Snapshots pages at specified breakpoints. Highlights diffs | Full-page visual regression |
| **BackstopJS** | Open-source. Configurable viewport testing | Budget-conscious teams |
| **Playwright** | Screenshot comparison built into E2E tests | Teams already using Playwright |

**Workflow:**
1. Designer approves a Storybook story or page screenshot as the reference baseline
2. Every code change generates new screenshots
3. Tool compares new screenshots against baseline
4. Differences are flagged for review
5. Designer approves or rejects changes

### Design Token Linting

Automated checks that enforce design token usage:

| Rule | What It Catches |
|------|----------------|
| **No hardcoded colors** | `color: #3B82F6` → should be `color: var(--color-primary)` |
| **No hardcoded spacing** | `margin: 16px` → should be `margin: var(--spacing-md)` |
| **No hardcoded typography** | `font-size: 14px` → should be `font-size: var(--text-sm)` |
| **No hardcoded border-radius** | `border-radius: 8px` → should be `border-radius: var(--radius-md)` |

**Tools:** Stylelint with custom rules, or design token-specific linters.

### Accessibility Automation

| Tool | What It Catches | Integration |
|------|----------------|-------------|
| **axe-core** | ~57% of WCAG issues | CI/CD, Storybook addon, browser extension |
| **Lighthouse** | Accessibility score + specific issues | CI/CD, Chrome DevTools |
| **Pa11y** | WCAG conformance checks | CI/CD |
| **jest-axe** | Accessibility issues in unit tests | Jest test suite |

**Note:** Automated tools catch ~30-50% of accessibility issues. Manual testing (keyboard, screen reader) is still required. Automate what you can, manually test the rest.
