# Error Prevention and Recovery

Error prevention hierarchy, undo patterns, inline validation, empty states, loading patterns, and recovery flows. Based on Cooper's About Face and Saffer's Microinteractions.

---

## The Error Prevention Hierarchy

Address errors in this order — prevention is always cheaper than recovery:

| Level | Approach | Example | Cost to User |
|-------|----------|---------|-------------|
| **1. Eliminate** | Remove the possibility of the error entirely | Auto-save eliminates "forgot to save." Dropdown eliminates misspelled country names | Zero |
| **2. Prevent** | Design inputs that make errors impossible | Date picker prevents invalid dates. Slider prevents out-of-range values | Zero |
| **3. Detect early** | Catch errors as they happen, before submission | Inline validation on field blur. Real-time format checking | Low |
| **4. Recover gracefully** | When errors occur, make recovery easy and painless | Undo after delete. Auto-correct with "Did you mean...?" | Medium |
| **5. Explain clearly** | If recovery requires user action, explain exactly what to do | Inline error with specific message + highlight + fix suggestion | Medium-High |
| **6. Diagnose** | Help users understand what went wrong and why | Detailed error page with troubleshooting steps | High |

Never design at Level 5-6 when you could design at Level 1-2.

---

## Inline Validation

### When to Validate

| Timing | How It Works | Best For |
|--------|-------------|----------|
| **On blur** (field exit) | Validate when user leaves the field | Most fields. Gives user time to finish typing |
| **On input** (real-time) | Validate as user types | Format-sensitive fields (phone, credit card). Show checkmarks as requirements are met |
| **On submit** | Validate all fields when form is submitted | Final check. Should rarely be the only validation |

**Rule:** Never validate on input for fields where the user is still typing valid content. "j" is not an invalid email — the user hasn't finished typing.

### Validation Message Design

| Element | Guideline |
|---------|-----------|
| **Placement** | Below the field, aligned with input text. Never in a separate error summary only |
| **Color** | `color-feedback-error` for border and message. Red icon (plus text — never color alone) |
| **Icon** | Error icon (!) next to message text. Provides a non-color signal |
| **Message** | Specific, actionable. "Enter a valid email (e.g., name@example.com)" not "Invalid input" |
| **Timing** | Appear on blur or after brief typing pause (300ms). Disappear as soon as the input is corrected |
| **Focus** | On submit with errors, focus the first error field. Scroll it into view if off-screen |

### Error Message Writing

| Bad | Good |
|-----|------|
| "Invalid input" | "Enter a number between 1 and 100" |
| "Error: field required" | "Email is required to create your account" |
| "Validation failed" | "This username is already taken. Try adding a number?" |
| "Error 422" | "We couldn't save your changes. Check the highlighted fields" |
| "Something went wrong" | "We couldn't connect to the server. Check your internet connection and try again" |

**Principles:**
1. **Say what happened** (briefly)
2. **Say what the user can do about it** (specifically)
3. **Never blame the user** ("We couldn't process" not "You entered an invalid")
4. **Never use jargon** (no error codes, no "validation", no "exception")

---

## Undo Patterns

### Undo Instead of Confirmation

Confirmation dialogs ("Are you sure?") are excise. They interrupt flow, and users learn to click "OK" without reading. **Undo is almost always better.**

| Confirmation Dialog | Undo Alternative |
|-------------------|-----------------|
| "Are you sure you want to delete?" | Delete immediately. Show "Undo" toast for 10 seconds |
| "Discard unsaved changes?" | Auto-save continuously. Nothing to discard |
| "Send this message?" | Send immediately. Show "Undo send" for 5 seconds |
| "Move to trash?" | Move immediately. "Moved to trash. Undo" |
| "Remove team member?" | Remove immediately. "Removed. Undo" (the member is just deactivated for the undo period) |

### When Confirmation IS Appropriate

Some actions genuinely warrant confirmation because they're:
- **Truly irreversible** — Permanently deleting data (not just moving to trash)
- **High-consequence** — Publishing to production, sending to 10,000 users, financial transactions
- **Affect others** — Removing someone's access, deleting shared resources

Even then, state the consequences specifically: "This will permanently delete 23 files. This cannot be undone." Not just "Are you sure?"

### Undo Implementation Patterns

| Pattern | How It Works | Duration |
|---------|-------------|----------|
| **Toast undo** | Action executes. Toast appears with "Undo" button. Clicking undoes the action | 5-10 seconds |
| **Soft delete** | Item is hidden/flagged, not actually deleted. Can be restored from trash | 30 days (typical) |
| **Multi-level undo** | Cmd+Z steps back through action history | Unlimited (within session) |
| **Version history** | Every save creates a version that can be restored | Persistent |
| **Draft recovery** | Work-in-progress is auto-saved. Can be restored if lost | 30 days (typical) |

---

## Empty States

Every screen that can display data must also handle having **no data**. Empty states are first impressions for new users and recovery moments for users who've cleared their content.

### Empty State Types

| Type | Cause | Design Response |
|------|-------|----------------|
| **First use** | User hasn't created anything yet | Welcome message + clear CTA ("Create your first project") |
| **No results** | Search or filter returned nothing | Explain why + suggest alternatives ("Try a different search term") |
| **Cleared** | User deleted all items | Acknowledge + offer to start fresh ("All done! Create a new task?") |
| **Error** | Data failed to load | Explain + offer retry ("Couldn't load your projects. Try again") |
| **Permission** | User doesn't have access | Explain + offer a path ("Ask your admin for access to this workspace") |

### Empty State Design Rules

1. **Never show a blank screen** — Always provide context and a path forward
2. **Show one primary action** — Not a menu of everything the user could do
3. **Use illustration sparingly** — A simple icon or illustration humanizes the moment, but it shouldn't dominate
4. **Match the tone** — First-use empty states can be welcoming. Error empty states should be empathetic
5. **Include educational content** — "Projects help you organize your team's work" — briefly explain the concept for new users

---

## Loading Patterns

### Choosing the Right Pattern

| Pattern | Duration | Best For |
|---------|----------|----------|
| **No indicator** | <100ms | Instant responses. No feedback needed |
| **Skeleton screen** | 100ms-3s | Content areas. Preserves layout. Reduces perceived wait time |
| **Spinner** | 500ms-10s | Indeterminate processes. Small area (button, card) |
| **Progress bar** | 2s-60s | Determinate processes. Upload, download, multi-step |
| **Background task** | >10s | Long processes. Let user continue other work. Notify on completion |

### Skeleton Screen Rules

- Match the layout of the actual content exactly — same heights, widths, spacing
- Use neutral gray blocks for text lines, rectangles for images, circles for avatars
- Animate with a subtle pulse or shimmer (left-to-right wave)
- Replace with real content via crossfade (150-200ms)
- Never show a skeleton for content that loads instantly

### Progress Indication Rules

1. **Show something within 1 second** — Even if you don't know how long it'll take, show a spinner
2. **Determinate > indeterminate** — If you know the progress, show a progress bar with percentage. Users prefer knowing "60% done" over an infinite spinner
3. **Estimate time when possible** — "About 2 minutes remaining" reduces anxiety
4. **Allow cancellation** — Any process over 5 seconds should have a cancel button
5. **Show what's happening** — "Uploading photo 3 of 7..." is better than just a progress bar
6. **Don't restart progress** — If a process has multiple stages, keep the bar moving forward, don't reset to 0%

---

## Recovery Flows

### Network Error Recovery

```
Action → Network Error
    → Show inline error: "Couldn't save. No internet connection."
    → Auto-retry silently in background (3 attempts, exponential backoff)
    → If reconnected: Save and show brief success confirmation
    → If still offline: "Still offline. Your changes are saved locally and will sync when you're back online."
```

### Server Error Recovery

```
Action → Server Error (500)
    → Show inline error: "Something went wrong on our end."
    → Offer retry button
    → Auto-retry once after 5 seconds
    → If persistent: "We're looking into this. Your work is saved locally."
    → Provide support link for critical flows
```

### Session Expiry Recovery

```
User Returns After Timeout
    → Silently attempt token refresh
    → If refresh succeeds: Continue seamlessly (user never knows)
    → If refresh fails: Overlay login prompt
    → After re-auth: Return user to exact state they were in
    → Never discard unsaved work due to session expiry
```

### Conflict Recovery

```
User Saves → Server Reports Conflict (another user edited)
    → Show both versions side-by-side
    → Let user choose: "Keep mine" / "Keep theirs" / "Merge"
    → Never silently overwrite another user's work
```
