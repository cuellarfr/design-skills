# Design Critique Walkthrough

End-to-end critique of a fictional SaaS dashboard for "MetricsPro," an analytics platform for marketing teams.

---

## Context

**Design:** MetricsPro main dashboard (home screen after login)
**Persona:** Jordan, marketing manager at a mid-size B2B company. Uses the dashboard daily to check campaign performance. Not technical — needs data in plain language.
**Primary task:** Quickly assess today's campaign performance and identify anything that needs attention.
**Fidelity:** High-fi mockup

---

## Design Description

The dashboard has:
- **Top bar:** Logo, search icon, notification bell, profile avatar
- **Left sidebar:** 8 navigation items with icons only (no labels): Dashboard, Campaigns, Audiences, Reports, Integrations, Settings, Help, What's New
- **Main area:**
  - Row of 6 KPI cards (Sessions, Users, Bounce Rate, Conversions, Revenue, CAC)
  - Large line chart (Sessions over time, last 30 days)
  - Two-column grid: Left = "Top Campaigns" table. Right = "Recent Activity" feed
- **Color:** Dark mode. Purple primary. Gray cards on dark gray background.

---

## Step 1: First Impression (5 Seconds)

- **What is this page about?** An analytics dashboard showing metrics
- **What is the primary action?** Unclear — there's no obvious CTA. Am I supposed to read the numbers? Click a campaign?
- **Where would I click first?** Probably one of the KPI cards, but they don't look clickable
- **Anything confusing?** The 8 icon-only nav items — I don't know what half of them mean

**First impression verdict:** The page communicates "analytics dashboard" but doesn't guide action. It's a display, not a tool.

---

## Step 2: Findings

### Finding 1: Icon-Only Navigation — Mystery Meat

**Severity:** 3 — Major
**Principle:** H6 (Recognition over Recall), Jakob's Law
**Location:** Left sidebar

**What's wrong:** All 8 navigation items are icons without text labels. The icons for "Audiences," "Integrations," and "What's New" are not standard and require memorization.

**Why it matters:** Jordan uses this daily, so she might learn the icons eventually — but new team members won't. And even Jordan will hesitate on infrequent items like "Integrations." Research shows icon-only navigation is consistently slower and less accurate than icon+label.

**Recommendation:** Add text labels next to every icon. If sidebar width is a concern, show labels on hover or use a collapsible sidebar (icon-only by default, labeled on expand). At minimum, add labels to the non-standard icons.

---

### Finding 2: KPI Cards — No Context or Direction

**Severity:** 3 — Major
**Principle:** H1 (Visibility of System Status), Mental Model
**Location:** KPI cards row

**What's wrong:** The 6 KPI cards show only current numbers with no comparison context:
- "Sessions: 14,832" — Is that good? Bad? Up or down from yesterday?
- "Bounce Rate: 47.3%" — Above or below target?
- No trends, no percentage changes, no targets.

**Why it matters:** Jordan's task is to "quickly assess performance and identify what needs attention." Raw numbers without context force her to remember yesterday's numbers or compare mentally. This violates both Recognition over Recall (H6) and puts cognitive load on the user (Tesler's Law — system should do the comparison).

**Recommendation:** Add comparison data to each card: percentage change vs. previous period (with up/down arrow and color coding), sparkline trend, and optional target indicator. Example: "Sessions: 14,832 ↑ 12% vs. last week" with a green up arrow.

---

### Finding 3: Six KPI Cards — Choice Overload

**Severity:** 2 — Moderate
**Principle:** Hick's Law, Miller's Law, Visual Hierarchy
**Location:** KPI cards row

**What's wrong:** All 6 cards have identical visual weight — same size, same styling, same emphasis. There's no hierarchy signaling which metrics are most important for Jordan.

**Why it matters:** When everything is equally prominent, nothing is prominent. Jordan scans all 6 every time instead of immediately seeing the 2-3 that matter most. This slows her daily check.

**Recommendation:** Two options:
1. **Highlight the top 2-3:** Make the most important KPIs (likely Conversions and Revenue) visually larger or use accent color
2. **Let users customize:** Allow users to choose which 3-4 KPIs appear in the top row and push the rest to a secondary area

---

### Finding 4: Dark Mode — Contrast Issues

**Severity:** 3 — Major
**Principle:** 1.4.3 (WCAG AA), Aesthetic-Usability Effect
**Location:** Entire dashboard

**What's wrong:** Purple text (#8B5CF6) on dark gray background (#1F2937) has a contrast ratio of approximately 3.8:1 — below the 4.5:1 AA requirement for normal text. Gray secondary text (#6B7280) on the same background is approximately 3.1:1.

**Why it matters:** Low contrast affects readability for all users, especially in varying lighting conditions. The dark mode aesthetic looks polished (Aesthetic-Usability Effect) but masks a real readability problem. Jordan may struggle with the secondary text, especially on laptop screens in bright offices.

**Recommendation:** Lighten the purple to at least #A78BFA (5.2:1) for primary text. Lighten gray text to at least #9CA3AF (4.6:1) for secondary text. Verify with WebAIM contrast checker.

---

### Finding 5: No Empty or Error States Designed

**Severity:** 2 — Moderate
**Principle:** H1 (Visibility), H9 (Error Recovery), Blank Slate pattern
**Location:** Entire dashboard

**What's wrong:** The mockup shows the dashboard fully populated with data. No designs for:
- What happens when a new user has no campaigns yet?
- What happens if the data API fails?
- What happens during initial data loading?
- What happens if a metric has no data for the selected period?

**Why it matters:** These states happen to every user. A blank dashboard with no guidance will confuse new users. A failed data load with no error message will make users think the product is broken.

**Recommendation:** Design four states:
1. **Empty state:** "Create your first campaign to see metrics here" + CTA button
2. **Loading state:** Skeleton screens for each card and chart
3. **Error state:** "Couldn't load campaign data. Check your integration settings or try again." + retry button
4. **Partial data:** Individual card-level "No data" state (not a whole-page error)

---

### Finding 6: Recent Activity Feed — Low Value

**Severity:** 1 — Minor
**Principle:** H8 (Aesthetic and Minimalist Design), Pareto Principle
**Location:** Right column, below chart

**What's wrong:** The "Recent Activity" feed shows system-generated events ("Campaign 'Summer Sale' was updated," "Report 'Q3 Overview' was generated"). This is noise for Jordan's primary task (assess performance).

**Why it matters:** The activity feed takes 50% of the width in the bottom section but provides low value for the primary persona. It competes with the "Top Campaigns" table which is more actionable.

**Recommendation:** Either (a) remove the activity feed from the dashboard and move it to a dedicated "Activity" page, or (b) reduce it to a narrow sidebar panel and give "Top Campaigns" the full width. The top campaigns table is what Jordan needs to act on.

---

### Finding 7: No Keyboard Navigation Support Visible

**Severity:** 2 — Moderate
**Principle:** H7 (Flexibility and Efficiency), Accessibility
**Location:** Entire dashboard

**What's wrong:** No visible focus states, no skip-link, no keyboard shortcut hints. For a daily-use tool, power users will want keyboard efficiency.

**Recommendation:** Add visible focus indicators, keyboard shortcut hints (press `?` to see shortcuts), and a skip-to-main link. For a dashboard used daily, keyboard shortcuts for common actions (e.g., `C` for campaigns, `R` for reports) significantly improve efficiency.

---

## What's Working Well

- **Layout structure is clear:** Three distinct zones (nav, KPIs, detail) follow a conventional dashboard pattern (Jakob's Law)
- **Single-page overview:** All key information visible without navigation — correct for a daily-check use case
- **Dark mode execution:** Consistent dark theme applied throughout — no light/dark inconsistencies
- **Top Campaigns table:** Sortable, shows key metrics per campaign — directly supports "what needs attention" task
- **Sessions chart:** Clean, readable line chart with appropriate time range (30 days)

---

## Missing States Check

| State | Present? | Notes |
|---|---|---|
| Default | Yes | Primary mockup |
| Hover | No | No hover states shown for cards, nav items, or table rows |
| Focus | No | No keyboard focus indicators |
| Disabled | N/A | No disabled elements in this view |
| Loading | No | No skeleton screens or loading states |
| Error | No | No error states for data failures |
| Success | N/A | No success-triggering actions on this page |
| Empty | No | No empty state for new users |

---

## Summary

| Severity | Count |
|---|---|
| 4 — Catastrophe | 0 |
| 3 — Major | 3 |
| 2 — Moderate | 3 |
| 1 — Minor | 1 |

### Top 3 Priorities

1. **KPI cards need context** (Severity 3) — Add comparison data, trends, and targets. This directly blocks the primary task.
2. **Fix contrast ratios** (Severity 3) — Purple and gray text fail WCAG AA. Lighten both.
3. **Add text labels to navigation** (Severity 3) — Icon-only nav fails recognition over recall.

### Suggested Next Steps

- [ ] Add comparison data to KPI cards and retest with 3 users
- [ ] Fix contrast ratios (quick win — CSS only)
- [ ] Add nav labels (or collapsible sidebar)
- [ ] Design missing states (empty, loading, error, hover, focus)
- [ ] Consider removing or deprioritizing the activity feed
- [ ] Add keyboard shortcut support for daily-use efficiency
