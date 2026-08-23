# Handoff Walkthrough

End-to-end handoff of a feature from design to engineering, including preparation, the handoff session, and post-handoff QA.

---

## Context

**Product:** TaskPilot — web-based task management app
**Feature:** Inline task editing — users can edit task title, due date, priority, and assignee directly from the task list without opening the detail panel
**Designer:** Jamie
**Engineer:** Sam (frontend) + Robin (backend)
**Sprint:** Sprint 14

**Why this feature:** The interaction audit (see interaction-design examples) identified that editing a task required opening a detail panel — 3 extra clicks for a quick change. Users edit tasks 12x/day on average. Reducing this to inline editing saves ~36 unnecessary clicks per day.

---

## Step 1: Pre-Handoff Preparation

### Jamie's Handoff Checklist

| Category | Check | Status |
|----------|-------|--------|
| **Screens** | All inline editing states designed | Done |
| **States** | Default, hover, editing, saving, error, disabled | Done |
| **Responsive** | Desktop (1440px), tablet (768px), mobile (320px) | Done |
| **Content** | Real task titles, dates, names. Character limits documented | Done |
| **Tokens** | All values reference TaskPilot design tokens | Done |
| **Components** | Uses existing TextInput, DatePicker, PrioritySelector, AvatarSelector | Done — no new components needed |
| **Accessibility** | Focus order, keyboard interaction, ARIA roles, screen reader announcements | Done |
| **Edge cases** | Long titles, past due dates, unassigned tasks, permission restrictions | Done |
| **Behavior notes** | Annotations on every frame | Done |

### Figma Organization

```
TaskPilot — Task List Inline Editing v1.0
├── 📄 Cover (status, links, changelog)
├── 📄 User Flow
│   └── Flow diagram: click-to-edit → edit → save/cancel
├── 📄 Task Title — Inline Edit
│   ├── Section: States (default, hover, editing, saving, error)
│   ├── Section: Responsive (desktop, tablet, mobile)
│   └── Section: Edge Cases (long title, empty title)
├── 📄 Due Date — Inline Edit
│   ├── Section: States
│   ├── Section: Responsive
│   └── Section: Edge Cases (past date, no date, date picker overflow)
├── 📄 Priority — Inline Edit
│   ├── Section: States
│   └── Section: Responsive
├── 📄 Assignee — Inline Edit
│   ├── Section: States
│   ├── Section: Responsive
│   └── Section: Edge Cases (unassigned, team > 10 people)
└── 📄 Keyboard Navigation
    └── Full tab order and keyboard interaction diagram
```

---

## Step 2: Behavior Documentation

Jamie writes behavior notes directly on the Figma frames AND in a summary document linked from the ticket.

### Task Title — Inline Edit

**Trigger:** Double-click on task title text, or focus the title with Tab and press Enter.

**Sequence:**
1. Title text transforms into a TextInput field (200ms crossfade)
2. Input is pre-filled with the current title, all text selected
3. User edits the text
4. Save on: Enter key, click outside (blur), or Tab to next field
5. Cancel on: Escape key (reverts to original title)
6. On save: input transforms back to text (150ms), API call fires
7. If API fails: text reverts, error toast appears

**States:**

| State | Visual | Trigger |
|-------|--------|---------|
| Default | Static text, `text-primary`, `font-weight-medium` | — |
| Hover | Text gets subtle underline indicator: 1px `color-border-secondary` | Mouse hover on title area |
| Editing | TextInput component, auto-focused, text selected, blue border `color-border-focus` | Double-click or Enter on focus |
| Saving | Text returns to static, brief pulse animation (opacity 100% → 80% → 100%, 300ms) | Enter, blur, or Tab |
| Error | Text reverts to pre-edit value. Toast: "Couldn't save. Try again." | API failure |
| Disabled | Static text, `text-tertiary`, no hover indicator | User doesn't have edit permission |

**Edge cases:**
- **Title > 200 characters:** TextInput shows character count after 180 characters. Hard limit at 200. "23 characters remaining"
- **Empty title:** Prevent saving empty. Show inline validation: "Task title is required." Input border changes to `color-border-error`
- **Title with only whitespace:** Trim whitespace. If empty after trim, treat as empty
- **Concurrent edit:** Last write wins. If another user edited the title while this user was editing, show: "This title was just updated by [Name]. Your change will overwrite theirs." with Save/Cancel options

**Tokens:**
```
Background (editing): color-bg-input
Border (editing): color-border-focus (2px)
Border (error): color-border-error (2px)
Text: text-primary
Placeholder: text-placeholder
Transition: duration-fast (150ms), easing-standard
```

### Due Date — Inline Edit

**Trigger:** Click on the due date text, or focus with Tab and press Enter/Space.

**Sequence:**
1. Date text is replaced by the DatePicker component (200ms, fade in from below)
2. DatePicker opens with current date selected (or today if no date set)
3. User selects a new date
4. On selection: DatePicker closes (150ms), new date displays, API call fires
5. Cancel on: Escape or click outside the DatePicker

**Edge cases:**
- **Past dates:** Allowed (tasks may have missed deadlines). Past dates show in `color-feedback-error`
- **No date set:** Shows "No due date" in `text-tertiary`. Click opens DatePicker with today highlighted
- **Date picker overflow:** On mobile, if the DatePicker would overflow the screen, it opens as a bottom sheet instead of a dropdown
- **Relative dates:** Display as relative when within 7 days ("Tomorrow," "In 3 days," "Yesterday"). Display as absolute date after 7 days ("Mar 28, 2026")

### Priority — Inline Edit

**Trigger:** Click on the priority indicator, or focus with Tab and press Enter/Space.

**Sequence:**
1. Priority dropdown opens below the indicator (150ms, slide down)
2. Current priority is highlighted
3. Options: Urgent (red), High (orange), Medium (yellow), Low (gray) — each with color dot AND text label
4. User clicks/selects a priority
5. Dropdown closes (100ms), indicator updates, API call fires

**Accessibility note:** Priority is communicated by both color AND text label, never color alone. Screen reader announces: "Priority: [level]. Press Enter to change."

### Assignee — Inline Edit

**Trigger:** Click on the assignee avatar, or focus with Tab and press Enter/Space.

**Sequence:**
1. Assignee popover opens (200ms, fade in) showing team members
2. Current assignee is highlighted with a checkmark
3. Search field at top for teams > 5 people (auto-focused)
4. User clicks a team member
5. Popover closes (150ms), avatar updates, API call fires

**Simplified from current design:** The current assignee flow requires 4 clicks (click → popover → search → select). The new design: click → popover with team visible → click to select. 2 clicks. Search is available but not required for small teams.

**Edge cases:**
- **Unassigned:** Shows a generic avatar placeholder with "+" icon. Click opens the same popover
- **Team > 10 people:** Search field is visible by default. Type to filter
- **Team <= 5 people:** No search field. All members visible at once
- **Removed team member:** If the assigned person left the team, show their avatar grayed out with a tooltip: "[Name] is no longer on this team. Reassign?"

---

## Step 3: Keyboard Navigation Spec

```
Tab order within a task row:
[Checkbox] → [Title] → [Priority] → [Due Date] → [Assignee] → [Next row's Checkbox]

Keyboard interactions:
- Checkbox: Space to toggle
- Title: Enter to start editing, Enter to save, Escape to cancel
- Priority: Enter/Space to open dropdown, Arrow Up/Down to navigate, Enter to select, Escape to close
- Due Date: Enter/Space to open DatePicker, Arrow keys to navigate dates, Enter to select, Escape to close
- Assignee: Enter/Space to open popover, Arrow Up/Down to navigate, Enter to select, Escape to close

Focus management:
- After saving a title edit (Enter): focus moves to Priority (next field in the row)
- After selecting a priority: focus returns to the Priority indicator (stays on the row)
- After Escape from any editor: focus returns to the element that opened the editor
- After Tab from the last field in a row: focus moves to the next row's Checkbox
```

---

## Step 4: Handoff Session

**Date:** Monday, Sprint 14, Day 1
**Attendees:** Jamie (designer), Sam (frontend), Robin (backend)
**Duration:** 40 minutes

### Walkthrough (15 min)

Jamie screen-shares Figma, walks through:
1. The user flow diagram — entry points, happy path, error paths
2. Each field's inline edit flow — title, due date, priority, assignee
3. Each state — with annotations visible

### States and Edge Cases (10 min)

Jamie specifically calls out:
- The concurrent edit handling for titles (Sam asks: "How often does this actually happen?" Robin: "Rare for tasks, but we should handle it")
- The date picker bottom sheet behavior on mobile (Sam: "We already have that pattern for the filter selector, so it's reusable")
- The assignee simplified flow (Robin: "Backend is the same — just a PATCH to the task. No new endpoints needed")

### Tokens and Components (5 min)

Jamie confirms:
- All four inline editors use existing components: TextInput, DatePicker, PrioritySelector, AvatarSelector
- No new components needed
- Token list is in the Figma annotations

### Questions (10 min)

| Question (from Sam) | Answer (from Jamie) |
|---------------------|---------------------|
| "What happens if the user double-clicks while a save is in progress?" | Debounce. If still saving, ignore the new double-click. Show the saving pulse animation |
| "Should the hover indicator show on touch devices?" | No. Touch devices go straight to editing on tap. No hover state |
| "Can users tab through and edit multiple fields without saving between each?" | Yes. Tab from title → priority opens the priority dropdown. Tabbing away from an edited field auto-saves it |
| "What's the character limit on task titles?" | 200 characters. Show count after 180. Enforce in both frontend and backend |

| Question (from Robin) | Answer (from Jamie / Sam) |
|------------------------|--------------------------|
| "Do we need a new API endpoint?" | No. Existing PATCH /tasks/:id handles all fields. Same payload |
| "Should saves be batched if user edits multiple fields quickly?" | No. Each field saves independently. Simpler, and the API is fast enough |

### Action Items

| Item | Owner | Due |
|------|-------|-----|
| Update TextInput to support the "saving pulse" animation | Sam | Wed |
| Confirm DatePicker bottom sheet works on iOS Safari | Sam | Tue |
| Add 200-char validation to task title endpoint | Robin | Tue |
| Create user stories in the sprint board (4 stories: title, date, priority, assignee) | Jamie + Maria (PM) | Mon afternoon |

---

## Step 5: Implementation

Sam and Robin build over the sprint. Jamie is available for questions.

**Mid-sprint check-in (Wednesday):**
- Sam shows the title inline edit working in Storybook
- Jamie reviews: "The save animation is slightly too fast — it should be 300ms, looks like 150ms. And the TextInput width should match the original title width, not the full row width"
- Sam adjusts. Jamie confirms in Storybook

---

## Step 6: Design QA

**When:** Thursday, Sprint 14 (before sprint review Friday)
**Where:** Staging environment
**Method:** Jamie reviews each story on staging, files issues

### QA Session Notes

**Task Title — Inline Edit:**

| Check | Result | Issue? |
|-------|--------|--------|
| Double-click activates edit | Pass | — |
| Text is pre-selected on edit | Pass | — |
| Enter saves | Pass | — |
| Escape cancels | Pass | — |
| Tab saves and moves to priority | Pass | — |
| Character count appears at 180 | Pass | — |
| Empty title prevented | Pass | — |
| Error toast on API failure | **Fail** | Toast doesn't appear. Error is logged to console only |
| Hover indicator | Pass | — |
| Focus ring on keyboard navigation | **Fail** | Focus ring is cut off on the left side — needs 2px offset |
| Responsive (mobile) | Pass | — |
| Screen reader announces editing mode | **Fail** | No announcement. Needs `aria-live` region |

**Due Date — Inline Edit:**

| Check | Result | Issue? |
|-------|--------|--------|
| Click opens DatePicker | Pass | — |
| Past dates show in red | Pass | — |
| Bottom sheet on mobile | **Fail** | Opens as dropdown on mobile, overflows off-screen |
| Relative dates ("Tomorrow") | Pass | — |
| Keyboard navigation in DatePicker | Pass | — |
| Escape closes without saving | Pass | — |

**Priority — Inline Edit:**

| Check | Result | Issue? |
|-------|--------|--------|
| Click opens dropdown | Pass | — |
| Text labels alongside colors | Pass | — |
| Keyboard navigation | Pass | — |
| Screen reader announcements | Pass | — |
| All states render correctly | Pass | — |

**Assignee — Inline Edit:**

| Check | Result | Issue? |
|-------|--------|--------|
| Click opens popover | Pass | — |
| Search works for large teams | Pass | — |
| Small teams show all members | Pass | — |
| Unassigned state | Pass | — |
| Keyboard navigation | **Fail** | Arrow keys don't work in the popover — Tab moves between names instead |

### Issues Filed

```
## Design QA: Inline Editing (Sprint 14)

### Task Title — 3 issues
1. [Major] Error toast doesn't appear on save failure.
   Expected: Toast "Couldn't save. Try again." at bottom of screen
   Actual: Error logged to console only. User has no feedback
   Fix: Wire up the error toast component to the save failure handler

2. [Minor] Focus ring clipped on left edge.
   Expected: 2px focus ring with 2px offset, fully visible
   Actual: Ring is clipped by the row's overflow:hidden
   Fix: Add overflow:visible to the task row during focus, or use outline-offset

3. [Major] Screen reader doesn't announce editing mode.
   Expected: "Editing task title" announced when edit mode activates
   Actual: No announcement
   Fix: Add aria-live region or role="status" that announces mode change

### Due Date — 1 issue
4. [Major] DatePicker overflows on mobile viewports.
   Expected: Bottom sheet presentation on viewports <768px
   Actual: Dropdown that overflows off the right edge
   Fix: Use the bottom sheet variant of DatePicker when viewport <768px

### Assignee — 1 issue
5. [Minor] Keyboard navigation uses Tab instead of Arrow keys in popover.
   Expected: Arrow Up/Down navigates between team members
   Actual: Tab navigates between team members
   Fix: Implement roving tabindex pattern (Arrow keys navigate, Tab exits)
```

### QA Results Summary

| Story | Issues | Severity | Status |
|-------|--------|----------|--------|
| Task title | 3 | 2 Major, 1 Minor | Needs fixes before release |
| Due date | 1 | 1 Major | Needs fix before release |
| Priority | 0 | — | Passed |
| Assignee | 1 | 1 Minor | Can ship, fix next sprint |
| **Total** | **5** | **3 Major, 2 Minor** | **3 must-fix, 2 can-defer** |

---

## Step 7: Fix and Re-QA

Sam fixes the 3 major issues by Friday morning. Jamie re-verifies:

| Issue | Fix Verified |
|-------|-------------|
| Error toast on title save failure | Pass — toast appears, auto-dismisses after 5s |
| Screen reader announces editing mode | Pass — "Editing task title" announced via aria-live |
| DatePicker bottom sheet on mobile | Pass — opens as bottom sheet below 768px |

The 2 minor issues (focus ring clipping, assignee keyboard nav) are added to the Sprint 15 backlog.

**Feature ships in Sprint 14 release.**

---

## Key Takeaways

1. **The pre-handoff checklist prevented omissions.** Without it, the concurrent edit handling and mobile DatePicker edge case would likely have been discovered in QA or production
2. **Behavior annotations on Figma frames** answered 80% of engineering questions before the handoff session. The session focused on the genuinely ambiguous parts
3. **Mid-sprint check-in** caught the animation timing issue early — a 5-minute fix on Wednesday instead of a QA issue on Thursday
4. **Design QA found 5 issues, 3 of them major.** Without QA, these would have shipped to users — including silent error handling and a screen reader gap
5. **The handoff session was 40 minutes** (not a thrown-over-the-wall Figma link). That 40-minute investment saved hours of back-and-forth during implementation
