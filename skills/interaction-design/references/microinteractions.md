# Microinteractions

The four-part framework in depth, with design patterns for triggers, rules, feedback, and loops/modes. Based on Dan Saffer's Microinteractions.

---

## Triggers in Depth

### Manual Trigger Patterns

| Pattern | Mechanism | Best For |
|---------|-----------|----------|
| **Button** | Click/tap to activate | Single, discrete actions (submit, save, send) |
| **Toggle** | Click/tap to switch between two states | Binary settings (on/off, show/hide, enabled/disabled) |
| **Slider** | Drag along a track | Continuous value within a range (volume, brightness) |
| **Stepper** | Click +/- to increment/decrement | Precise numeric input with small range (quantity, font size) |
| **Gesture** | Swipe, pinch, long-press | Spatial or navigation interactions (swipe to delete, pinch to zoom) |
| **Voice** | Spoken command | Hands-free contexts, accessibility, smart assistants |
| **Keyboard shortcut** | Key combination | Frequent actions for power users (Cmd+S, Ctrl+Z) |
| **Hover** | Cursor enters element area | Preview, tooltip, additional options (desktop only) |

### System Trigger Patterns

| Pattern | Condition | Example |
|---------|-----------|---------|
| **Time-based** | Clock reaches a time, duration expires | Alarm fires, session timeout, scheduled notification |
| **Location-based** | Device enters/leaves a geofence | "You're near the store" reminder |
| **State change** | Data or connection state changes | New message received, network restored, download complete |
| **Threshold** | A value crosses a boundary | Battery below 20%, storage nearly full |
| **Error detection** | System detects an anomaly | Failed sync, broken link, invalid data |
| **Inactivity** | User hasn't interacted for N seconds | Auto-save, screen dim, session warning |

### Bringing Data Forward

The most effective triggers **surface information** from inside the interaction on the trigger itself:

| Trigger | Without Data | With Data Forward |
|---------|-------------|------------------|
| Mail icon | Envelope icon | Envelope icon + "3" badge (3 unread) |
| Battery indicator | Battery icon | Battery icon + "47%" + charging bolt |
| Download button | "Download" | "Download (2.3 MB)" |
| Sync button | Circular arrows | Circular arrows + "Last synced 5 min ago" |
| Notification bell | Bell icon | Bell icon + red dot (new notifications) |
| Settings toggle | "Notifications: Settings" | "Notifications: On (3 channels)" |

This reduces the need to "open to check" — a common source of navigational excise.

---

## Rules in Depth

### Rule Design Checklist

For every microinteraction, define:

- [ ] **What happens** when the trigger fires (the primary action)
- [ ] **What the user can control** (parameters, options)
- [ ] **What the user cannot do** (constraints, disabled states)
- [ ] **The sequence of steps** (if multi-step)
- [ ] **How the system responds to valid input**
- [ ] **How the system responds to invalid input** (error prevention first, then error handling)
- [ ] **What data is used** (pre-filled, remembered, derived)
- [ ] **How the interaction ends** (what state does the system return to?)
- [ ] **What the system remembers** (for next time)

### Smart Defaults

| Principle | Example |
|-----------|---------|
| **Remember last value** | Last-used save location, last-selected format, last search query |
| **Use context** | Prefill city from GPS. Default to user's timezone. Suggest recent contacts |
| **Use frequency** | Most-used option first. Recently-used items at top |
| **Use the data** | If the user entered a phone number, default country code from their profile |
| **Progressive defaults** | First time: guide with defaults. Repeat: use the user's previous choices |

**Rule:** If it was worth it to the user to enter it, it's worth it to the application to remember it (Cooper).

### Error Prevention (Poka-Yoke)

Design inputs that make errors impossible:

| Technique | How | Example |
|-----------|-----|---------|
| **Constrained input** | Limit options to valid values | Dropdown instead of free text for country. Date picker instead of text field |
| **Forgiving formats** | Accept multiple input formats | Phone number accepts "(555) 123-4567" or "5551234567" or "+1 555-123-4567" |
| **Real-time validation** | Check as user types, not after submit | Email field shows error before user moves to next field |
| **Smart parsing** | Interpret ambiguous input intelligently | "next tuesday" → Tuesday March 31, 2026 |
| **Undo over prevention** | Let users act freely, provide easy reversal | Delete immediately + "Undo" toast > "Are you sure?" dialog |
| **Physical constraints** | Design controls that can't produce invalid states | Slider can't go below 0 or above 100 |

---

## Feedback in Depth

### Visual Feedback Patterns

| Pattern | Duration | Use Case |
|---------|----------|----------|
| **Color change** | 150-300ms transition | State change (active, selected, error) |
| **Checkmark/icon swap** | 200-400ms | Action confirmation (saved, sent, copied) |
| **Progress bar** | Duration of process | Determinate processes (upload, download, form completion) |
| **Spinner** | Until complete | Indeterminate processes (loading, searching) |
| **Skeleton screen** | Until content loads | Content areas replacing with actual data |
| **Toast/snackbar** | 3-5 seconds auto-dismiss | Non-critical confirmations ("Item saved," "Link copied") |
| **Inline message** | Until resolved | Validation errors, field-level guidance |
| **Badge/dot** | Until acknowledged | Notifications, unread counts, status changes |
| **Shake/bounce** | 300-600ms | Invalid input, boundary reached |
| **Highlight/pulse** | 1-2 seconds | Drawing attention to a change or new element |

### Feedback Intensity Scale

Match feedback intensity to message importance:

| Importance | Intensity | Example |
|-----------|-----------|---------|
| **Low** (routine confirmation) | Subtle — small icon change, brief toast | "Settings saved" toast |
| **Medium** (status change) | Moderate — visible animation, color change | Toggle switch animates on/off |
| **High** (error, warning) | Strong — persistent message, accent color, icon | Inline error message with red border |
| **Critical** (data loss risk) | Maximum — modal, blocking, requires action | "Unsaved changes will be lost. Save now?" |

### Auditory Feedback Guidelines

- **Use sound to reinforce, not replace** visual feedback — some users have sound off
- **Short sounds** (50-200ms) for confirmations — longer sounds for completion
- **Positive sounds** for success (ascending tone). **Neutral sounds** for alerts. Avoid harsh negative sounds
- **Provide volume control** and a mute option for all sounds
- **Don't play sounds for repeated routine actions** — a sound for every keystroke becomes maddening

### Haptic Feedback Guidelines

- **Light tap** — Routine confirmation (toggle, selection)
- **Medium tap** — Boundary reached (end of scrollable list, slider endpoint)
- **Heavy tap** — Error or significant event (failed action, important alert)
- **Pattern** — Specific notification type (different vibration for message vs. call)

---

## Loops and Modes in Depth

### Long Loops (The Long Wow)

Design the interaction across its entire lifecycle:

| Phase | User State | Design Response |
|-------|-----------|-----------------|
| **First use** | Uncertain, exploring | Guided defaults, contextual hints, generous feedback |
| **Learning** (days 2-7) | Building mental model | Reduce guidance, introduce shortcuts, remember preferences |
| **Regular use** (weeks) | Intermediate, efficient | Streamlined flow, keyboard shortcuts, reduced feedback for known actions |
| **Return after absence** | Partially forgotten | "Welcome back" re-orientation, highlight what changed, preserve state |
| **Expert use** (months+) | Power user | Advanced features discoverable, customization, batch operations |

### Progressive Disclosure Over Time

| First Use | After 5 Uses | After 50 Uses |
|-----------|-------------|---------------|
| Tooltip hints on all controls | Hints only on less-used controls | No hints (but available on hover) |
| Onboarding walkthrough | "Tip of the day" (dismissible) | Nothing — user knows the product |
| Default view with essential options | "Show advanced" toggle remembered | Advanced always visible (if user toggled it) |
| Confirmation dialogs for destructive actions | "Don't ask again" checkbox | Skip confirmation, rely on Undo |

### Mode Design Rules

1. **Zero modes is ideal** — Can you achieve this without a mode? Try harder
2. **One mode maximum per microinteraction** — More creates confusion
3. **Make the mode unmistakable** — If the user can't tell which mode they're in at a glance, the design has failed
4. **Prefer spring-loaded modes** — Active only while held (long-press for selection mode, Shift for multi-select). Users always know because they're actively holding
5. **One-off modes auto-revert** — Use for rare, single actions. The mode fires once and returns to normal
6. **Settings modes on separate screens** — Don't interleave settings with primary interaction

---

## Microinteraction Quality Checklist

When reviewing a microinteraction:

- [ ] **Trigger** is discoverable and its state is clear (normal, hover, disabled, updated)
- [ ] **Data is brought forward** where possible (badges, counts, current values on the trigger)
- [ ] **Rules** handle valid input, invalid input, empty input, and edge cases
- [ ] **Smart defaults** reduce work (remembered values, contextual pre-fill)
- [ ] **Feedback** is proportional to importance (subtle for routine, prominent for errors)
- [ ] **Visual + auditory + haptic** channels used appropriately (not relying on one alone)
- [ ] **Feedback doesn't block interaction** (toasts over modals; inline over interrupting)
- [ ] **Modes** are minimized (0-1) and clearly indicated
- [ ] **Long loop** considered (first use vs. regular use vs. return)
- [ ] **Error prevention** precedes error handling (constraints, smart parsing, forgiving formats)
- [ ] **Undo** is available for destructive actions (instead of confirmation dialogs)
- [ ] **Keyboard accessible** — interaction works without a mouse/touch
- [ ] **Reduced motion** alternative exists (instant state change, no animation)
