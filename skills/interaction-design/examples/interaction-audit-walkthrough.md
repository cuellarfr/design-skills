# Interaction Audit Walkthrough

Auditing and improving interactions in a fictional task management product.

---

## Context

**Product:** TaskPilot — a web-based task management app for small teams
**Trigger:** Users complain the app "feels clunky" despite the UI looking clean. Support tickets about lost work and confusing behavior are rising. The team suspects interaction design issues rather than visual design problems.
**Scope:** The main task list view — the screen users spend 80% of their time on.

---

## Step 1: Identify All Interactive Elements

Walk through the task list screen and catalog every element that responds to user input:

| # | Element | Type | Location |
|---|---------|------|----------|
| 1 | Task checkbox | Toggle | Left of each task row |
| 2 | Task title | Text (clickable) | Center of each task row |
| 3 | Priority selector | Dropdown | Right of task title |
| 4 | Due date | Date picker trigger | Right of priority |
| 5 | Assignee avatar | Clickable avatar | Right of due date |
| 6 | "Add task" button | Button | Bottom of task list |
| 7 | Task row (entire) | Clickable area | Full row |
| 8 | Drag handle | Drag target | Left edge (hidden until hover) |
| 9 | Sort controls | Dropdown | List header |
| 10 | Filter controls | Multi-select | List header |
| 11 | Search input | Text field | Top of page |
| 12 | Keyboard shortcuts | Hidden | Global |

---

## Step 2: State Inventory

Audit each element's states. Mark gaps.

### Task Checkbox

| State | Designed? | Issue |
|-------|----------|-------|
| Default (unchecked) | Yes | OK |
| Checked | Yes | OK |
| Hover | **No** | No hover feedback — users aren't sure if it's clickable |
| Focus | **No** | Can't tab to checkboxes — keyboard users can't complete tasks |
| Disabled | **No** | What happens during sync? Can users check offline tasks? |
| Loading (syncing) | **No** | Checkbox changes instantly but there's no feedback if sync fails |
| Error (sync failed) | **No** | If the server rejects the change, the checkbox stays checked — data mismatch |

**Issues found:** 4 missing states. Keyboard inaccessible. No error handling for sync failures.

### Task Title (Click to Open Detail)

| State | Designed? | Issue |
|-------|----------|-------|
| Default | Yes | OK |
| Hover | **Partially** | Text underlines on hover, but the entire row also has a hover state — two competing hover effects |
| Focus | **No** | Can't keyboard-navigate to task titles |
| Truncated (long title) | Yes | Ellipsis, but no tooltip showing full title |
| Empty | **No** | What if a task has no title? Blank space with no affordance |

### "Add Task" Button

| State | Designed? | Issue |
|-------|----------|-------|
| Default | Yes | OK |
| Hover | Yes | OK |
| Focus | **No** | Can't tab to it |
| Active | Yes | OK |
| Loading (creating) | **No** | Button doesn't change during task creation — user clicks multiple times, creating duplicate tasks |
| Disabled | **No** | Should it be disabled while another task is being created? |

### Drag Handle for Reordering

| State | Designed? | Issue |
|-------|----------|-------|
| Default | Hidden until row hover | OK for mouse users |
| Hover on handle | Yes | Cursor changes to grab |
| Dragging | **Partially** | Row lifts but no drop zone indicators. User can't tell where the task will land |
| Drop | **No** | Task snaps to position with no animation — feels jarring |
| **Keyboard alternative** | **Missing entirely** | No way to reorder with keyboard |
| **Touch alternative** | **Missing** | No drag affordance on mobile. Long-press doesn't work |

---

## Step 3: Identify Excise

### Navigational Excise
- **Editing a task requires opening the detail panel:** Click task → panel opens on right → make changes → close panel. For quick edits (changing a due date), this is 3 extra clicks. The due date picker is visible on the row but only for display — can't edit inline
- **Assigning a task requires 4 clicks:** Click assignee → popover opens → search for person → click person → popover closes. Most teams have 5-10 people. A simple dropdown would be 2 clicks

### Modal Excise
- **"Are you sure you want to delete this task?"** — Every single time. No undo option. The dialog doesn't even say which task is being deleted

### Cognitive Excise
- **Priority levels are colors only:** Red, orange, yellow, gray. No labels. New users must learn the color code. Color-blind users can't distinguish orange from red

### Physical Excise
- **"Add task" button is at the bottom of the list:** For long lists, user must scroll to the bottom to add a task. Should be at the top or accessible via keyboard shortcut

---

## Step 4: Prioritize Improvements

Rank by frequency × severity:

| # | Issue | Frequency | Severity | Fix |
|---|-------|-----------|----------|-----|
| 1 | No keyboard navigation | Every session for keyboard users | High — accessibility violation | Add tabindex, focus styles, Enter/Space to activate |
| 2 | Duplicate tasks on double-click | Multiple times/day | High — data corruption | Disable button during creation. Debounce |
| 3 | No sync error handling on checkbox | Every session | High — silent data loss | Optimistic UI + revert on failure + error toast |
| 4 | Inline editing blocked | Multiple times/day | Medium — excessive navigation | Enable inline edit for title, due date, priority, assignee |
| 5 | Delete confirmation without undo | Weekly | Medium — excise | Remove dialog. Add undo toast (10 seconds) |
| 6 | Drag-and-drop missing feedback | Weekly | Medium — confusing | Add drop zone indicators, animation, keyboard alternative |
| 7 | Priority colors without labels | First use + ongoing for color-blind | Medium — accessibility | Add text labels alongside colors |
| 8 | "Add task" at bottom only | Multiple times/day | Low-Medium — physical excise | Add to top + Cmd+N keyboard shortcut |

---

## Step 5: Redesign Top Issues

### Fix #1: Keyboard Navigation

**Before:** Tab key skips the task list entirely. Only mouse interaction.

**After:**
- Tab enters the task list. Arrow keys navigate between tasks
- Each task is a composite widget: Tab stops on the row, then Arrow Right moves between checkbox → title → priority → due date → assignee
- Enter on checkbox: toggle complete. Enter on title: open detail. Space on priority: open dropdown
- Focus ring: 2px `color-border-focus`, clearly visible on every focusable element

### Fix #2: Prevent Duplicate Tasks

**Before:** Click "Add task." Nothing visible happens for 500ms while the API creates the task. User clicks again. Two tasks created.

**After:**
- Click "Add task" → button immediately shows spinner + "Creating..." text → button is disabled
- New task row appears with cursor in the title field (optimistic UI)
- API confirms → spinner disappears → button re-enables
- If API fails → task row shows error state ("Couldn't create task. Try again?")

**State machine:**
```
[Ready] --click--> [Creating] --success--> [Ready] + new task in list
                              --error--> [Ready] + error toast
```

### Fix #3: Sync Error Handling

**Before:** User checks a task. Checkbox fills immediately. API call fails silently. User thinks the task is complete. It isn't.

**After:**
- User checks task → checkbox fills immediately (optimistic)
- API call fires
- If success: task gets a brief green flash (100ms) and subtitle shows "Just now"
- If failure: checkbox reverts to unchecked (150ms crossfade). Toast: "Couldn't mark complete. Try again." Task row briefly highlights in `color-feedback-error` background (1 second fade)
- Auto-retry once after 3 seconds. If retry succeeds, update silently

### Fix #5: Undo Instead of Confirmation

**Before:** Click delete → "Are you sure you want to delete this task?" → OK/Cancel

**After:**
- Click delete → task immediately fades out and collapses (200ms)
- Toast appears at bottom: "[Task title] deleted. **Undo** (10s)"
- If undo clicked: task smoothly expands back into its original position (200ms)
- If 10 seconds pass: toast dismisses. Task is permanently deleted (soft-delete for 30 days, actually)
- Keyboard: Cmd+Z also undoes the last delete within the 10-second window

---

## Step 6: Measure Impact

### Metrics to Track

| Metric | Before | Target | How to Measure |
|--------|--------|--------|---------------|
| Duplicate task creation rate | ~8% of sessions | <1% | Count tasks created within 2 seconds of each other |
| Checkbox sync failure rate (unnoticed) | Unknown — no tracking | 0% unnoticed | Track revert events vs. silent failures |
| Delete confirmation dialog dismissal | 73% always click OK | N/A (dialog removed) | Track undo usage rate (expect 5-10% of deletes are undone) |
| Tasks completed via keyboard | 0% | Measurable usage | Track completion events with keyboard flag |
| "Feels clunky" support tickets | 12/month | <3/month | Tag and count support tickets |

---

## Key Takeaways

1. **"Feels clunky" is almost always an interaction problem, not a visual one.** The UI looked fine — the behavior was broken
2. **The state inventory revealed 15+ missing states** across 12 elements. Each missing state is a potential bug or user frustration
3. **Excise was the biggest contributor to "clunky" feeling.** Four extra clicks to edit a due date. A confirmation dialog on every delete. Scrolling to add a task. These individually seem minor but compound into a sluggish experience
4. **Optimistic UI with error recovery** is almost always better than waiting for server confirmation. Users get instant feedback, and errors are handled gracefully instead of blocking the happy path
5. **Keyboard accessibility wasn't just an accessibility issue** — it was a power-user productivity issue. Many users prefer keyboard for task management
