# Microinteraction Spec: [Interaction Name]

**Component/Feature:** [Where this interaction lives]
**Version:** [1.0.0]
**Owner:** [Person]
**Last updated:** [Date]

---

## Goal

[One sentence: What is the user trying to accomplish with this interaction?]

---

## 1. Trigger

### Type
[ ] Manual (user-initiated) / [ ] System (automatic)

### Mechanism
[How is the interaction initiated? Button, toggle, gesture, keyboard shortcut, system event, time-based?]

### Trigger States

| State | Visual Treatment | When |
|-------|-----------------|------|
| Default | [Description] | Ready to be activated |
| Hover | [Description] | Cursor over (desktop) |
| Focus | [Description] | Keyboard navigation |
| Active | [Description] | Being pressed |
| Disabled | [Description] | Not currently available |
| Updated | [Description] | Something changed since last interaction |

### Data Brought Forward
[What information is shown on the trigger before activation? Badge count, current value, status?]

---

## 2. Rules

### Primary Action
[What happens when the trigger is activated?]

### Sequence
1. [First thing that happens]
2. [Second thing]
3. [Third thing]
4. [Final state]

### User Controls
[What can the user adjust? Parameters, options, settings?]

### Constraints
[What can't the user do? Limits, disabled actions, maximum values?]

### Smart Defaults
[What values are pre-filled or remembered? What does the system infer?]

### Edge Cases

| Edge Case | Handling |
|-----------|---------|
| Empty input | [What happens] |
| Maximum value exceeded | [What happens] |
| Network failure during action | [What happens] |
| Action interrupted (user navigates away) | [What happens] |
| Concurrent action by another user | [What happens] |
| [Other edge case] | [What happens] |

### How It Ends
[What state does the system return to after the interaction completes?]

### What the System Remembers
[What values, settings, or choices does the system remember for next time?]

---

## 3. Feedback

### Visual Feedback

| Moment | Feedback | Duration | Intensity |
|--------|----------|----------|-----------|
| Trigger activated | [Description] | [ms] | [Subtle/Moderate/Strong] |
| Processing | [Description] | [Until complete] | [Intensity] |
| Success | [Description] | [ms or auto-dismiss time] | [Intensity] |
| Error | [Description] | [Until resolved] | [Intensity] |

### Auditory Feedback
[If applicable: What sounds play and when? Is there a mute option?]

### Haptic Feedback
[If applicable: What vibration patterns and when?]

### Motion

| Animation | Duration | Easing | Reduced Motion Alternative |
|-----------|----------|--------|--------------------------|
| [Description] | [ms] | [Curve] | [Instant state change / fade only] |
| [Description] | [ms] | [Curve] | [Alternative] |

### Tokens Used
```
[Token references for colors, durations, easing curves]
```

---

## 4. Loops & Modes

### Loops
| Type | Behavior |
|------|---------|
| **Retry on failure** | [How many times? Backoff strategy?] |
| **Auto-refresh** | [Does it poll? At what interval?] |
| **Repeat** | [Can the user repeat the action? How?] |

### Modes
[Are there any modes? If so, describe each:]

| Mode | Trigger | Indicator | How to Exit |
|------|---------|-----------|-------------|
| [Mode name] | [How user enters] | [How they know they're in it] | [How they leave] |

### Long Loop (Lifecycle)

| Phase | Behavior |
|-------|---------|
| First use | [Onboarding hints? Guided defaults?] |
| Regular use | [Streamlined? Reduced feedback?] |
| Return after absence | [Re-orientation? What's changed?] |
| Power user | [Shortcuts? Advanced options?] |

---

## 5. Accessibility

| Requirement | Implementation |
|-------------|---------------|
| Keyboard trigger | [Key or key combination] |
| Focus management | [Where does focus go?] |
| Screen reader announcement | [What is announced at each stage?] |
| Color independence | [How is information conveyed without color?] |
| Reduced motion | [Alternative for prefers-reduced-motion] |
| Touch target | [Minimum size] |

---

## 6. State Machine

```
[State diagram showing all states and transitions]
Example:
[Idle] --trigger--> [Processing] --success--> [Complete]
                                  --error--> [Error]
[Error] --retry--> [Processing]
[Complete] --reset--> [Idle]
```

---

## Related Interactions
| Interaction | Relationship |
|------------|-------------|
| [Name] | [How they relate — triggers after, alternative path, etc.] |
