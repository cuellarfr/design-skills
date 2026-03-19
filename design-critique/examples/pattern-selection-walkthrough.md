# Pattern Selection Walkthrough

End-to-end example of evaluating and selecting interaction patterns for a fictional project management tool, "TaskFlow."

---

## Context

**Product:** TaskFlow — a project management SaaS for small teams (5-15 people)
**Feature:** Task creation and assignment flow
**Persona:** Sam, a project manager at a 10-person agency. Creates 5-10 tasks daily. Not technical but comfortable with tools like Trello and Asana. Moves fast between meetings.
**Primary task:** Quickly create a task, assign it to a team member, and set a due date.
**Current design:** A full-page form with 12 fields opened via a "New Task" button in the top nav.

---

## Step 1: Posture Analysis

**Question:** What posture does TaskFlow have?

TaskFlow is a **sovereign-posture** app. Sam has it open all day alongside email and Slack. She switches to it frequently but in short bursts (create a task, check a board, update status).

**Implication:** The task creation flow is a **transient interaction within a sovereign app**. It should:
- Be fast — Sam does this 5-10 times a day
- Not take her away from the board view
- Remember her habits (last project, common assignees)

**Current design problem:** A full-page form for a transient interaction is a posture mismatch. It navigates Sam away from her board, breaking flow.

---

## Step 2: Excise Audit

Evaluating the current 12-field form for unnecessary work:

| Field | Necessary? | Excise Type | Fix |
|---|---|---|---|
| Task title | Yes — core | — | Keep |
| Description | Yes — but optional | — | Keep, but don't require |
| Project | Yes — context | Navigational (could be inferred) | Default to current project |
| Assignee | Yes — delegation | Memory (Sam remembers team members) | Autocomplete with recent assignees |
| Due date | Yes — scheduling | Physical (date picker requires clicks) | Smart defaults ("Tomorrow", "Next Monday", natural language) |
| Priority | Useful | Cognitive (what do the 5 levels mean?) | Reduce to 3: Low/Medium/High. Default to Medium |
| Status | No — always "To Do" on creation | Full excise | Remove — auto-set to "To Do" |
| Estimated hours | Rarely used | Full excise for most tasks | Move to task detail (progressive disclosure) |
| Tags | Optional | Memory (remembering tag names) | Move to task detail; autocomplete if kept |
| Start date | Rarely used | Full excise | Move to task detail |
| Attachments | Optional | Physical (file picker) | Move to task detail; allow adding after creation |
| Watchers | Optional | Cognitive (who should watch?) | Auto-add assignee and creator; move manual adding to task detail |

**Result:** 12 fields → 5 for quick creation (title, description, project, assignee, due date) + 2 visible but optional (priority, tags). The remaining 5 move to the task detail view.

**Excise eliminated:**
- Status field (always "To Do") — removed
- Estimated hours, start date — moved to detail (progressive disclosure)
- Attachments, watchers — moved to detail

---

## Step 3: Pattern Selection

### Primary Pattern: Inline Quick-Create

**Pattern chosen:** Inplace Editor / Expandable Input
**Why:** Sam's primary task is transient (quick creation). She shouldn't leave the board.

**Implementation:**
1. Clicking "+" or pressing `N` on the board opens an inline card at the top of the "To Do" column
2. Card shows: title field (auto-focused), assignee picker, due date picker
3. Pressing Enter creates the task. Pressing Escape cancels.
4. After creation, the card stays open for another task (batch creation).

**Pattern alternatives considered:**

| Pattern | Why Not |
|---|---|
| Full-page form | Posture mismatch — breaks flow for a transient task |
| Modal | Better than full-page but still interrupts. Reserve for the "detailed creation" path |
| Floating panel | Good alternative if more fields are needed. Could be a secondary path |

### Secondary Pattern: Modal for Detailed Creation

**Pattern chosen:** Modal with progressive fields
**Why:** Sometimes Sam needs to create a fully specified task (with description, attachments, specific dates). The inline quick-create is too constrained.

**Implementation:**
1. Keyboard shortcut `Shift+N` or "Create task with details" option opens a modal
2. Modal shows the 5 core fields + expandable "More options" section
3. "More options" reveals: estimated hours, start date, attachments, watchers
4. Modal remembers whether "More options" was expanded (sticky preference)

### Supporting Patterns

| Pattern | Where | Why |
|---|---|---|
| **Good Defaults** | Project field, priority, status | Reduce fields Sam needs to touch. Project = current board. Priority = Medium. Status = To Do |
| **Autocomplete** | Assignee field | Sam types first letters of name; recent assignees appear first |
| **Forgiving Format** | Due date | Accept "tomorrow", "next fri", "March 5", "3/5" — parse intelligently |
| **Keyboard Shortcuts** | Board view | `N` = quick create, `Shift+N` = detailed create, `Enter` = save |
| **Autosave** | Detailed modal | If Sam accidentally closes the modal, draft is preserved |
| **Undo** | After creation | Toast: "Task created" with [Undo] link for 5 seconds |

---

## Step 4: Interaction Design Evaluation

Evaluating the proposed design against interaction design principles:

### Orchestration Check

| Principle | Evaluation | Score |
|---|---|---|
| Follow mental models | Board → add card to column matches how Sam thinks about tasks | Pass |
| Less is more | Quick-create shows 3 fields, not 12 | Pass |
| Direct over discuss | Inline card creation, not a dialog asking questions | Pass |
| Choices over questions | Assignee picker with avatars, not a text field asking "Who?" | Pass |
| Tools close at hand | `N` shortcut available from any board view | Pass |
| Modeless feedback | Toast notification after creation, not a modal confirmation | Pass |
| Design for the probable | Quick-create optimized for the 80% case (simple task) | Pass |
| Hide the ejector seat | Bulk operations and task deletion are in menus, not inline | Pass |

### Perpetual Intermediate Check

| Concern | Evaluation |
|---|---|
| Does the quick-create serve intermediates? | Yes — fast, minimal, uses their working set of fields |
| Can beginners figure it out? | Yes — "+" button is visible; tooltip shows `N` shortcut (memorization vector) |
| Can experts go faster? | Yes — `N` creates inline, `Enter` saves, full keyboard flow |
| Are there memorization vectors? | Yes — tooltip on "+" shows shortcut; menu shows "New Task (N)" |

### Excise Check

| Excise Type | Before | After |
|---|---|---|
| Navigational | Leave board → full-page form → return to board | Stay on board; create inline |
| Cognitive | 12 fields, 5 priority levels, unclear required fields | 3-5 fields, 3 priority levels, smart defaults |
| Memory | Remember tag names, estimate formats | Autocomplete for tags, natural language for dates |
| Physical | Mouse to nav → click → fill 12 fields → click save → click back | `N` → type title → `Tab` → pick assignee → `Tab` → type date → `Enter` |
| Modal | Confirmation dialog on save | No confirmation; undo toast instead |

**Keystroke count for "Create a task assigned to Alex due tomorrow":**

- Before: ~18 clicks/tabs + typing
- After: `N` → "Review wireframes" → `Tab` → "al" → `Enter` (select Alex) → `Tab` → "tom" → `Enter` = ~12 keystrokes + typing

---

## Step 5: Missing States

| State | Designed? | Implementation |
|---|---|---|
| Default | Yes | Empty inline card with placeholder "Task title..." |
| Hover | Yes | "+" button highlights; assignee avatars show name tooltip |
| Focus | Yes | Active field has visible blue outline (2px) |
| Loading | Yes | Brief spinner on save; optimistic UI shows task immediately |
| Error | Yes | Red inline message if title is empty on Enter; "Couldn't save — retry" if API fails |
| Empty | Yes | Board column with no tasks shows "No tasks yet. Press N to create one" |
| Success | Yes | Toast: "Task created" with [Undo] [View] links, auto-dismiss after 5s |
| Offline | Yes | Task saved locally; synced when connection returns; offline indicator in status bar |

---

## Step 6: Summary

### Patterns Used

| Pattern | Purpose | UX Laws |
|---|---|---|
| Inplace Editor | Quick inline task creation | Direct Manipulation, Fitts's Law |
| Modal | Detailed task creation | Selective Attention, Progressive Disclosure |
| Good Defaults | Pre-fill project, priority, status | Tesler's Law |
| Autocomplete | Fast assignee selection | Recognition over Recall (H6) |
| Forgiving Format | Natural language dates | Postel's Law |
| Keyboard Shortcuts | Expert efficiency | H7 (Flexibility) |
| Autosave | Draft preservation | H5 (Error Prevention) |
| Undo | Post-creation recovery | H3 (User Control) |

### Key Decisions

1. **Inline over full-page** — Posture analysis revealed the task creation is transient within a sovereign app. Inline matches the posture.
2. **Two paths: quick + detailed** — 80% of tasks are quick assignments. 20% need more detail. Progressive disclosure via two entry points.
3. **Smart defaults over empty fields** — Project inferred from current board. Priority defaults to Medium. Status always "To Do." Reduces 12 fields to 3-5.
4. **Undo over confirm** — Task creation is frequent and reversible. Confirmation dialogs add modal excise 5-10 times per day. Undo toast is faster and non-blocking.
5. **Keyboard-first design** — Sam creates tasks between meetings. Full keyboard flow (N → type → Tab → type → Enter) takes 3 seconds vs. 15+ seconds for the form.

### Before/After

**Before:** Full-page form with 12 fields. ~18 interactions per task. Flow broken every time.
**After:** Inline quick-create with 3 fields + smart defaults. ~8 interactions per task. Flow preserved. Detailed modal available when needed.

**Expected impact:** Task creation time drops from ~30 seconds to ~8 seconds. Board abandonment during creation eliminated. User satisfaction with task creation improves (measure via in-app survey or NPS segment).
