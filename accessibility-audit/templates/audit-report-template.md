# Accessibility Audit Report

## Audit Overview

- **Product/Page:** [What was audited]
- **URL(s):** [Specific URLs tested]
- **Date:** [Audit date]
- **Auditor:** [Name]
- **Target conformance:** WCAG 2.2 Level [A / AA / AAA]
- **Testing methods:** [Automated scan, keyboard testing, screen reader testing, visual review]
- **Tools used:** [axe DevTools, WAVE, VoiceOver, NVDA, Chrome DevTools, etc.]
- **Browsers/devices:** [Chrome on macOS, Safari on iOS, etc.]

---

## Executive Summary

> 3-5 bullet points that a stakeholder can read in 30 seconds.

- **Overall conformance:** [Passes / Does not pass] WCAG 2.2 Level [AA]
- **Total issues found:** [#] ([#] Critical, [#] High, [#] Moderate, [#] Low)
- **Top finding:** [Most impactful issue — one sentence]
- **Biggest quick win:** [Easiest high-impact fix — one sentence]
- **Recommendation:** [Overall next step]

---

## Score Summary

### By Severity

| Severity | Count | % of Total |
|---|---|---|
| Critical | _ | _% |
| High | _ | _% |
| Moderate | _ | _% |
| Low | _ | _% |
| **Total** | **_** | **100%** |

### By WCAG Principle

| Principle | Issues | Most Common |
|---|---|---|
| Perceivable | _ | [Top issue] |
| Operable | _ | [Top issue] |
| Understandable | _ | [Top issue] |
| Robust | _ | [Top issue] |

### Automated Tool Score

| Tool | Score | Notes |
|---|---|---|
| Lighthouse Accessibility | _/100 | [Brief note] |
| axe DevTools | _ violations, _ passes | [Brief note] |

---

## Findings

### Finding 1: [Issue title]

**Severity:** Critical / High / Moderate / Low
**WCAG Criterion:** [Number] — [Name] (Level [A/AA/AAA])
**Principle:** Perceivable / Operable / Understandable / Robust
**Location:** [Page, component, or element where the issue occurs]
**Affects:** [Screen reader users / Keyboard users / Low vision users / Cognitive disabilities / All users]

**Description:**
[What the issue is and why it matters]

**Steps to reproduce:**
1. [Step]
2. [Step]
3. [Observe: description of the problem]

**Current code:**
```html
[Code showing the issue]
```

**Recommended fix:**
```html
[Code showing the fix]
```

**Effort:** Small / Medium / Large

---

### Finding 2: [Issue title]

**Severity:** Critical / High / Moderate / Low
**WCAG Criterion:** [Number] — [Name] (Level [A/AA/AAA])
**Principle:** Perceivable / Operable / Understandable / Robust
**Location:** [Page, component, or element]
**Affects:** [User groups]

**Description:**
[What and why]

**Steps to reproduce:**
1. [Step]

**Current code:**
```html
[Code]
```

**Recommended fix:**
```html
[Code]
```

**Effort:** Small / Medium / Large

---

### Finding 3: [Issue title]

[Same structure as above]

---

## Prioritized Remediation Plan

| Priority | Finding | WCAG | Severity | Effort | Tier | Owner |
|---|---|---|---|---|---|---|
| 1 | [Finding title] | [Criterion] | Critical | Small | 1 | [Team] |
| 2 | [Finding title] | [Criterion] | High | Medium | 1 | [Team] |
| 3 | [Finding title] | [Criterion] | High | Small | 1 | [Team] |
| 4 | [Finding title] | [Criterion] | Moderate | Medium | 2 | [Team] |
| 5 | [Finding title] | [Criterion] | Low | Small | 2 | [Team] |
| 6 | [Finding title] | [Criterion] | Low | Large | 3 | [Team] |

**Tier definitions:**
- **Tier 1:** Fix before next release — Critical/High severity or Level A violations
- **Tier 2:** Fix within current quarter — Moderate severity or Level AA violations
- **Tier 3:** Add to backlog — Low severity or Level AAA aspirational improvements

---

## What Passed

> Highlight what's working well. This encourages teams and identifies patterns to replicate.

- [Positive finding 1 — e.g., "All form inputs have programmatic labels"]
- [Positive finding 2 — e.g., "Keyboard navigation order is logical throughout"]
- [Positive finding 3 — e.g., "Error messages are descriptive and linked to fields"]
- [Positive finding 4 — e.g., "Skip navigation is present and functional"]

---

## Testing Details

### Pages/Flows Tested

| # | Page/Flow | URL | Issues Found |
|---|---|---|---|
| 1 | [Page name] | [URL] | [#] |
| 2 | [Page name] | [URL] | [#] |
| 3 | [Page name] | [URL] | [#] |

### Keyboard Testing Results

| Page | All elements reachable? | Focus visible? | Focus order logical? | No traps? | Notes |
|---|---|---|---|---|---|
| [Page] | Yes / No | Yes / No | Yes / No | Yes / No | [Notes] |

### Screen Reader Testing Results

| Page | Headings logical? | Landmarks present? | Labels announced? | Errors announced? | Notes |
|---|---|---|---|---|---|
| [Page] | Yes / No | Yes / No | Yes / No | Yes / No | [Notes] |

---

## Recommendations for Ongoing Compliance

- [ ] **Add automated testing to CI/CD** — Use axe-core in Playwright/Cypress/Jest to prevent regressions
- [ ] **Include accessibility in design reviews** — Check contrast, focus states, and heading hierarchy in Figma
- [ ] **Include accessibility in code reviews** — Use the Quick Audit Checklist (see SKILL.md)
- [ ] **Test with screen reader monthly** — Assign rotating responsibility
- [ ] **Re-audit after fixes** — Verify Tier 1 fixes before release
- [ ] **Schedule full re-audit** — [Recommended date, typically quarterly]

---

## Appendix

### Tools Used

- [Tool 1]: [Version, settings]
- [Tool 2]: [Version, settings]

### Standards Reference

- [WCAG 2.2](https://www.w3.org/TR/WCAG22/)
- [WebAIM WCAG Checklist](https://webaim.org/standards/wcag/checklist)
- [ARIA Authoring Practices](https://www.w3.org/WAI/ARIA/apg/)
