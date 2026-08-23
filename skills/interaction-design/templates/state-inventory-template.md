# State Inventory: [Feature/Screen Name]

**Date:** [Date]
**Auditor:** [Name]
**Scope:** [Which screen, feature, or flow is covered]

---

## Instructions

For every interactive element in the feature, document all possible states. Use this template to identify missing states — any cell with "Not designed" represents a potential bug or poor user experience.

---

## Interactive Elements

### [Element 1 Name] (e.g., "Save Button")

| State | Designed? | Visual Treatment | Notes |
|-------|----------|-----------------|-------|
| Default | [ ] Yes / [ ] No | [Description] | |
| Hover | [ ] Yes / [ ] No / [ ] N/A | [Description] | N/A for touch-only |
| Focus | [ ] Yes / [ ] No | [Description] | Must have visible focus ring |
| Active/Pressed | [ ] Yes / [ ] No | [Description] | |
| Disabled | [ ] Yes / [ ] No | [Description] | When is it disabled? |
| Loading | [ ] Yes / [ ] No / [ ] N/A | [Description] | |
| Success | [ ] Yes / [ ] No / [ ] N/A | [Description] | |
| Error | [ ] Yes / [ ] No / [ ] N/A | [Description] | |

### [Element 2 Name] (e.g., "Email Input")

| State | Designed? | Visual Treatment | Notes |
|-------|----------|-----------------|-------|
| Empty (placeholder) | [ ] Yes / [ ] No | [Description] | |
| Focused (empty) | [ ] Yes / [ ] No | [Description] | |
| Filled (valid) | [ ] Yes / [ ] No | [Description] | |
| Filled (invalid) | [ ] Yes / [ ] No | [Description] | When validated? |
| Disabled | [ ] Yes / [ ] No | [Description] | |
| Read-only | [ ] Yes / [ ] No / [ ] N/A | [Description] | |
| Error (with message) | [ ] Yes / [ ] No | [Description] | Message text? |

### [Element 3 Name] (e.g., "Data Table")

| State | Designed? | Visual Treatment | Notes |
|-------|----------|-----------------|-------|
| Loading | [ ] Yes / [ ] No | [Description] | Skeleton? Spinner? |
| Empty (no data) | [ ] Yes / [ ] No | [Description] | What CTA? |
| Populated | [ ] Yes / [ ] No | [Description] | |
| Error (failed to load) | [ ] Yes / [ ] No | [Description] | Retry option? |
| Filtered (no results) | [ ] Yes / [ ] No | [Description] | Clear filters CTA? |
| Selected row(s) | [ ] Yes / [ ] No | [Description] | Bulk actions? |
| Sorting | [ ] Yes / [ ] No | [Description] | Active sort indicator? |

[Repeat for each interactive element]

---

## Page-Level States

| State | Designed? | Description | Notes |
|-------|----------|------------|-------|
| First visit (new user) | [ ] Yes / [ ] No | [Description] | Onboarding? |
| Populated (normal use) | [ ] Yes / [ ] No | [Description] | |
| Loading (initial) | [ ] Yes / [ ] No | [Description] | Full skeleton? |
| Loading (refresh) | [ ] Yes / [ ] No | [Description] | Partial? Pull-to-refresh? |
| Offline | [ ] Yes / [ ] No | [Description] | Cached data? Banner? |
| Error (page-level) | [ ] Yes / [ ] No | [Description] | Retry? Fallback? |
| Unauthorized | [ ] Yes / [ ] No | [Description] | Login prompt? Request access? |
| Responsive (mobile) | [ ] Yes / [ ] No | [Description] | Layout changes? |
| Responsive (tablet) | [ ] Yes / [ ] No | [Description] | |
| Print | [ ] Yes / [ ] No / [ ] N/A | [Description] | |

---

## Transitions

| From State | To State | Trigger | Animation | Duration |
|-----------|---------|---------|-----------|----------|
| Loading | Populated | Data received | [Crossfade/slide/none] | [ms] |
| Populated | Loading | Refresh triggered | [Description] | [ms] |
| Populated | Error | Request failed | [Description] | [ms] |
| Error | Loading | Retry clicked | [Description] | [ms] |
| [From] | [To] | [Trigger] | [Animation] | [Duration] |

---

## Coverage Summary

| Category | Total States | Designed | Missing | Coverage |
|----------|-------------|----------|---------|----------|
| Element states | [#] | [#] | [#] | [%] |
| Page-level states | [#] | [#] | [#] | [%] |
| Transitions | [#] | [#] | [#] | [%] |
| **Total** | **[#]** | **[#]** | **[#]** | **[%]** |

---

## Priority Gaps

List the most impactful missing states:

| # | Missing State | Element | Impact | Priority |
|---|-------------|---------|--------|----------|
| 1 | [Description] | [Element] | [User impact if not designed] | [High/Med/Low] |
| 2 | [Description] | [Element] | [Impact] | [Priority] |
| 3 | [Description] | [Element] | [Impact] | [Priority] |
