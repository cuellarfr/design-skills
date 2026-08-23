# State and Transitions

State machines for UI, gesture patterns, keyboard interaction, drag-and-drop, and responsive behavior.

---

## State Machines for UI

### Why State Machines

Most interaction bugs are **state bugs**: the UI shows something that shouldn't be possible, or transitions between states are missing or broken. Modeling interactions as state machines prevents this by making states explicit and transitions enumerable.

### Anatomy of a State Machine

```
States:         The finite set of conditions the UI can be in
Events:         User actions or system events that trigger transitions
Transitions:    Movement from one state to another in response to an event
Actions:        Side effects that happen during a transition (API calls, animations, data updates)
Guards:         Conditions that must be true for a transition to occur
```

### Building a State Machine

**Step 1: List all possible states**

For a form submission:
```
Idle → Editing → Validating → Submitting → Success → Error
```

**Step 2: List all events**

```
user_types, user_submits, validation_passes, validation_fails,
server_responds_ok, server_responds_error, user_retries, user_resets
```

**Step 3: Define transitions**

| From State | Event | To State | Action |
|-----------|-------|----------|--------|
| Idle | user_types | Editing | Enable submit button |
| Editing | user_submits | Validating | Run client-side validation |
| Validating | validation_passes | Submitting | Send API request |
| Validating | validation_fails | Editing | Show inline errors |
| Submitting | server_responds_ok | Success | Show success message |
| Submitting | server_responds_error | Error | Show error + retry option |
| Error | user_retries | Submitting | Resend API request |
| Error | user_resets | Idle | Clear form |
| Success | user_resets | Idle | Clear form |

**Step 4: Verify impossible states**

Check that the machine prevents nonsensical combinations:
- Can't submit while already submitting (no transition from Submitting on user_submits)
- Can't show success and error simultaneously (they're different states)
- Can't edit while submitting (Submitting only transitions on server events)

### Parallel States

Some UI elements have independent state dimensions that operate simultaneously:

```
Form State:       Idle | Editing | Submitting | Success | Error
Connection State: Online | Offline | Reconnecting
Sidebar State:    Open | Closed
```

These run in parallel. The form can be in "Editing" while the connection is "Offline" and the sidebar is "Closed." Model them as separate machines, not one combined machine (which would have state explosion).

### Nested States (Statecharts)

When a state has sub-states, use David Harel's statecharts:

```
Authenticated
├── Dashboard
│   ├── Overview (default)
│   └── Detailed
├── Settings
│   ├── Profile
│   └── Notifications
└── Editor
    ├── Editing
    └── Previewing
```

The user is always in "Authenticated" AND one of its child states. Entering "Authenticated" defaults to "Dashboard > Overview." This reduces the number of transitions needed.

---

## Gesture Patterns

### Touch Gesture Catalog

| Gesture | Fingers | Motion | Standard Action | Discoverability |
|---------|---------|--------|----------------|-----------------|
| **Tap** | 1 | Touch + release | Select, activate | High — visible targets |
| **Double tap** | 1 | 2 rapid taps | Zoom in, select word | Medium — learned convention |
| **Long press** | 1 | Touch + hold (>500ms) | Context menu, selection mode, drag start | Low — always provide visible alternative |
| **Swipe** | 1 | Touch + horizontal/vertical drag | Navigate, dismiss, reveal actions | Medium — hints help on first use |
| **Drag** | 1 | Touch + move continuously | Reorder, move, resize | Low — needs affordance (handle icon) |
| **Pinch** | 2 | Two fingers move toward each other | Zoom out | Low — learned convention |
| **Spread** | 2 | Two fingers move apart | Zoom in | Low — learned convention |
| **Rotate** | 2 | Two fingers rotate around center | Rotate image/object | Very low — use only for spatial apps |
| **Edge swipe** | 1 | Swipe from screen edge | System navigation (back, drawer) | Low — platform-specific |

### Swipe Action Patterns

For list items with swipe-to-reveal actions:

| Direction | Convention | Example |
|-----------|-----------|---------|
| **Swipe left** | Destructive/secondary action | Delete, archive, dismiss |
| **Swipe right** | Constructive/primary action | Mark as done, accept, favorite |
| **Partial swipe** | Reveal action buttons | Show "Delete" and "Archive" buttons |
| **Full swipe** | Execute most common action | Swipe fully right to mark as read |

**Rules:**
- Show a preview of the action during the swipe (icon + color + label)
- Provide haptic feedback at the commitment threshold
- Allow the user to cancel by reversing the swipe before releasing
- Never make swipe the only way to access an action

### Drag and Drop

**During drag:**
- Element elevates (shadow increase) to show it's "lifted"
- Ghost/placeholder remains at origin to show where it came from
- Valid drop targets highlight as the element passes over them
- Invalid areas dim or show a "forbidden" cursor

**On drop:**
- Element animates to its new position (200-300ms ease-out)
- Origin placeholder collapses
- System provides feedback (haptic + visual) confirming the move

**Keyboard alternative:**
- Select item with Space/Enter
- Move with Arrow keys
- Confirm placement with Space/Enter
- Cancel with Escape

---

## Keyboard Interaction

### Focus Management

| Principle | Implementation |
|-----------|---------------|
| **Visible focus** | 2px focus ring, 3:1 contrast. Never remove `:focus` styles without replacement |
| **Logical tab order** | Tab follows visual reading order (left-to-right, top-to-bottom in LTR layouts) |
| **Focus trapping** | Modal dialogs trap focus inside. Tab from last element returns to first. Escape closes |
| **Focus restoration** | When a modal/popover closes, return focus to the element that opened it |
| **Skip navigation** | "Skip to main content" link as first focusable element on pages |
| **Focus on dynamic content** | When content loads or changes, move focus to the new content or announce it |

### Standard Keyboard Patterns

| Key | Standard Action |
|-----|----------------|
| **Tab** | Move focus to next interactive element |
| **Shift+Tab** | Move focus to previous interactive element |
| **Enter** | Activate focused button/link. Submit form |
| **Space** | Toggle checkbox/toggle. Activate button. Scroll page (no focused element) |
| **Escape** | Close modal/popover/dropdown. Cancel current action. Exit mode |
| **Arrow keys** | Navigate within a component (tabs, menus, radio groups, grids) |
| **Home/End** | First/last item in a list, menu, or tab set |

### Roving Tabindex

For composite widgets (tab bars, toolbars, menus):
- The component itself gets one tab stop
- Arrow keys navigate between items within the component
- This prevents Tab from walking through every item in a long list

---

## Responsive Interaction Behavior

### Adaptation by Input Method

| Input | Characteristics | Design Adjustments |
|-------|----------------|-------------------|
| **Mouse** | Precise, hover available, right-click | Small targets OK (min 24px). Hover states. Context menus |
| **Touch** | Imprecise, no hover, gestures available | Large targets (min 44px). Long-press for context. Swipe gestures |
| **Keyboard** | Sequential, no pointing | Visible focus, logical tab order, keyboard shortcuts |
| **Voice** | Hands-free, error-prone | Clear confirmation, undo, disambiguation |
| **Gamepad** | D-pad navigation, limited buttons | Focus-based navigation, large selection areas, simple actions |

### Adaptation by Screen Size

| Breakpoint | Interaction Changes |
|-----------|-------------------|
| **Desktop (>1024px)** | Multi-column layouts. Hover interactions. Side panels. Drag and drop. Keyboard shortcuts prominent |
| **Tablet (768-1024px)** | Touch-optimized. Larger tap targets. Swipe gestures. Reduced hover dependency. Collapsible panels |
| **Mobile (<768px)** | Single column. Bottom navigation. Full-screen modals. Sheet-style panels. Pull to refresh. Gesture-heavy |

### Interaction Breakpoints

Some interactions should fundamentally change at certain screen sizes:

| Desktop | Mobile |
|---------|--------|
| Hover dropdown menu | Tap to open, tap to close |
| Drag-and-drop reorder | Hold-to-drag or explicit "Edit order" mode |
| Right-click context menu | Long-press or "..." overflow button |
| Multi-select with Ctrl+Click | Selection mode toggle + tap to select |
| Side-by-side comparison | Swipe between / toggle between |
| Tooltips on hover | Tap-and-hold or info icon |
