# Handoff Checklist: [Feature Name]

**Designer:** [Name]
**Engineer(s):** [Names]
**Sprint:** [Sprint number or date range]
**Figma:** [Link to handoff frames]
**Ticket:** [Link to user story / issue]

---

## Pre-Handoff Verification

### Completeness

| Check | Status | Notes |
|-------|--------|-------|
| All screens in the flow are designed | [ ] | |
| Happy path flow complete | [ ] | |
| Error paths designed | [ ] | |
| Empty states designed | [ ] | |
| Loading states designed | [ ] | |
| Edge cases addressed | [ ] | |

### States Coverage

For each interactive element, verify these states exist:

| Element | Default | Hover | Focus | Active | Disabled | Loading | Error | Success |
|---------|---------|-------|-------|--------|----------|---------|-------|---------|
| [Element 1] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| [Element 2] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| [Element 3] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |
| [Element 4] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] | [ ] |

### Responsive

| Breakpoint | Designed? | Notes |
|-----------|----------|-------|
| Mobile (320px) | [ ] | |
| Mobile L (414px) | [ ] | |
| Tablet (768px) | [ ] | |
| Desktop (1024px) | [ ] | |
| Desktop L (1440px) | [ ] | |

### Design System

| Check | Status | Notes |
|-------|--------|-------|
| Uses existing design system components | [ ] | List any new components needed: |
| All values use design tokens (no raw hex/px) | [ ] | |
| Component names match code names | [ ] | |
| New components spec'd (if applicable) | [ ] | |

### Content

| Check | Status | Notes |
|-------|--------|-------|
| Real copy (no lorem ipsum) | [ ] | |
| Character limits documented | [ ] | |
| Truncation rules specified | [ ] | |
| Localization notes (if applicable) | [ ] | |
| Pluralization handled | [ ] | |

### Accessibility

| Check | Status | Notes |
|-------|--------|-------|
| Focus order documented | [ ] | |
| ARIA roles specified | [ ] | |
| Screen reader announcements documented | [ ] | |
| Color contrast verified (4.5:1 text, 3:1 UI) | [ ] | |
| Touch targets 44px+ | [ ] | |
| Keyboard interactions documented | [ ] | |

### Assets

| Check | Status | Notes |
|-------|--------|-------|
| Icons exported as SVG | [ ] | |
| Images have alt text | [ ] | |
| Animation specs provided | [ ] | |
| Fonts confirmed available | [ ] | |

---

## Behavior Documentation

### User Flow

```
[Entry point] → [Screen 1] → [Action] → [Screen 2] → ... → [End state]
                                ↳ [Error] → [Error screen] → [Recovery]
```

### Interactions

| Element | Trigger | Behavior | Animation |
|---------|---------|----------|-----------|
| [Element] | [Click/tap/hover/key] | [What happens] | [Duration, easing] |
| [Element] | [Click/tap/hover/key] | [What happens] | [Duration, easing] |
| [Element] | [Click/tap/hover/key] | [What happens] | [Duration, easing] |

### API Dependencies

| Screen/Action | API Endpoint | Loading State | Error State |
|--------------|-------------|--------------|------------|
| [Screen] | [Endpoint] | [What shows] | [What shows] |
| [Action] | [Endpoint] | [What shows] | [What shows] |

---

## Handoff Session

**Date:** [Date]
**Attendees:** [Names]
**Duration:** [Time]

### Questions from Engineering

| Question | Answer | Action Needed? |
|----------|--------|---------------|
| [Question] | [Answer] | [ ] Yes / [x] No |
| [Question] | [Answer] | [ ] Yes / [x] No |

### Open Items

| Item | Owner | Due |
|------|-------|-----|
| [Item] | [Name] | [Date] |
| [Item] | [Name] | [Date] |

---

## Post-Handoff

### Design QA

| Screen | QA Status | Issues |
|--------|----------|--------|
| [Screen 1] | [ ] Not started / [ ] In progress / [ ] Passed | [Link to issues] |
| [Screen 2] | [ ] Not started / [ ] In progress / [ ] Passed | [Link to issues] |
| [Screen 3] | [ ] Not started / [ ] In progress / [ ] Passed | [Link to issues] |

### Change Requests (Post-Handoff)

| Change | Reason | Impact | Priority |
|--------|--------|--------|----------|
| [What changed] | [Why] | [Which stories affected] | [Must-have / Nice-to-have] |

---

## Sign-Off

| Role | Name | Approved | Date |
|------|------|----------|------|
| Designer | [Name] | [ ] | [Date] |
| Engineer | [Name] | [ ] | [Date] |
| PM | [Name] | [ ] | [Date] |
