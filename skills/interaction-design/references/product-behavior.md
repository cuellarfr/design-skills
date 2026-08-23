# Product Behavior

Product postures, smart and considerate behavior, orchestration, flow, and excise elimination. Based on Alan Cooper's About Face.

---

## Product Postures

### Sovereign Applications

Apps that monopolize attention for extended periods. Users keep them running continuously, often maximized.

**Examples:** Email clients, IDEs, design tools, spreadsheets, project management.

**Design rules:**
- **Be generous with screen real estate** — Use the full screen. Dense information display is appropriate
- **Muted visual style** — Users stare at these for hours. Avoid saturated colors for chrome. Reserve color for data and status
- **Rich input support** — Direct manipulation, keyboard shortcuts, customizable toolbars. Target perpetual intermediates
- **Rich feedback** — Detailed status bars, progress indicators, inline validation. Users are invested enough to want detailed information
- **Design for documents** — Maximize content area. Minimize UI chrome
- **Provide multiple command modalities** — Menus (discoverable), toolbars (accessible), keyboard shortcuts (fast)

### Transient Applications

Apps that appear briefly, serve a purpose, and disappear. Users don't invest in learning them.

**Examples:** Calculators, settings panels, dialog boxes, dashboard widgets, installers.

**Design rules:**
- **Make it immediately obvious** — Users won't learn your transient app. It must be self-evident
- **Bright and clear visual style** — Unlike sovereign apps, transient ones should be visually distinctive to draw attention and communicate quickly
- **Minimal options** — Show only what's needed for this interaction
- **Remember user choices** — Even though it's transient, remember settings between sessions
- **Fast to invoke, fast to dismiss** — Keyboard shortcut to open. Escape to close. Click outside to dismiss

### Daemonic Applications

Apps that run invisibly in the background, serving without user interaction.

**Examples:** Print spoolers, backup services, sync agents, virus scanners, notification services.

**Design rules:**
- **Invisible when working correctly** — Don't notify users of routine success
- **Surface immediately when there's a problem** — A failed backup requires attention
- **Configure via transient settings panel** — System preferences, control panels
- **Provide status on demand** — Menu bar icon, system tray indicator. Users should be able to check status when they want, not be force-fed it
- **Fail gracefully and recover automatically** — Retry before alerting. Only alert the user when human intervention is actually needed

---

## Smart and Considerate Product Behavior

### Considerate Products (Cooper)

Design products that behave like a thoughtful human colleague:

| Principle | What It Means | Example |
|-----------|-------------|---------|
| **Take an interest** | Remember habits and everything the user tells you | Remember last-used settings, recently accessed files, preferred views |
| **Be forthcoming** | Volunteer useful information at appropriate moments | "You have a meeting in 15 minutes" — without being asked |
| **Anticipate needs** | Predict what the user will do based on what they've done | Pre-download the next page, pre-populate related fields |
| **Use common sense** | Don't do obviously wrong things | Don't auto-save an empty file over a full one |
| **Be conscientious** | Remember details and stay consistent | Same interaction works the same way everywhere |
| **Don't burden with internal problems** | Handle technical issues internally | Retry a failed network request before showing an error |
| **Keep informed** | Provide status without being asked | Background processes show progress in the status bar |
| **Fail gracefully** | When things go wrong, recover or degrade with dignity | Save a draft before crashing. Restore state on restart |
| **Help avoid mistakes** | Prevent errors rather than reporting them | Gray out unavailable options. Constrain inputs to valid ranges |
| **Take responsibility** | Treat user mistakes as system design failures | "We couldn't process your request" not "Invalid input" |

### Smart Products

| Principle | Implementation |
|-----------|---------------|
| **Put idle cycles to work** | Pre-compute, prefetch, index, compress while user isn't actively requesting |
| **Remember everything** | If the user configured it, the app remembers it. File locations, window sizes, sort orders, view preferences |
| **Use task coherence** | What the user did yesterday is likely similar to what they'll do today. Use recent behavior as the basis for defaults |
| **Multi-session memory** | Undo history, recent files, draft recovery should persist across sessions |
| **Predictive behavior** | Autocomplete, smart suggestions, pre-filled forms based on context |

---

## Orchestration

### Definition

All elements in an interface must work together coherently. When orchestration is good, the interface becomes invisible — users focus on their work, not on the tool.

### Orchestration Principles

1. **Follow mental models** — Design based on how users think, not how the system is built. The represented model (what users see) should match the mental model (what users expect), not the implementation model (how it actually works)
2. **Provide choices, don't ask questions** — "Bold / Italic / Underline" toggles > "How would you like to format this text?" dialog
3. **Keep tools close at hand** — Contextual toolbars near selection. Right-click menus at cursor. Inline editing where the content lives
4. **Provide modeless feedback** — Status information visible in the interface, not in dialog boxes. Errors inline, not in pop-ups where possible
5. **Design for the probable, anticipate the possible** — Optimize the most common path. Make the edge case possible but not in the way
6. **Reflect status** — Every data object and process should communicate its current state through visual cues
7. **Avoid blank slates** — Empty screens should guide users toward action: "No projects yet. Create your first project to get started"
8. **Differentiate command from configuration** — Commands (action buttons, direct manipulation) are for regular use. Configuration (settings panels) is for occasional setup. Don't mix them

---

## Flow

### What Breaks Flow

| Flow Breaker | Why It's Damaging | Alternative |
|-------------|-------------------|-------------|
| **Modal error dialogs** | Stop all work. Force the user to deal with the system's problem | Inline errors. Auto-recovery. Undo |
| **Confirmation dialogs** | Interrupt for routine actions. Users learn to click "OK" without reading | Undo instead of permission |
| **Context switching** | Navigating away from current work to perform a related function | In-context panels, popovers, inline editing |
| **Re-entering data** | Typing information the system already has | Auto-fill, smart defaults, remembered values |
| **Waiting without feedback** | User doesn't know if the system is working | Immediate skeleton/spinner, progress indication |
| **Required sequential steps** | Forcing users through a wizard when they know what they want | Allow direct access for experienced users. Wizard for first-timers |
| **Unnecessary notifications** | Alerts for non-urgent information | Quiet indicators (badges, dots). Reserve alerts for urgent items |

---

## Excise Audit

### How to Conduct an Excise Audit

1. **Define the goal path** — What is the user trying to accomplish? Map the ideal path from intent to completion
2. **Map the actual path** — Walk through the current product interaction step by step
3. **Label each step** — Is it goal-directed (directly advancing the user's objective) or excise (overhead that doesn't contribute)?
4. **Categorize excise** — Cognitive, memory, visual, or physical?
5. **Score severity** — How much does this excise cost the user in time, effort, or frustration?
6. **Prioritize elimination** — Highest-severity excise that affects the most users first

### Excise Reduction Techniques

| Excise Type | Reduction Technique |
|-------------|-------------------|
| **Cognitive** | Clear labels. Consistent patterns. Match mental models. Reduce jargon |
| **Memory** | Remember settings. Show recent items. Auto-fill. Provide search |
| **Visual** | Clear hierarchy. Adequate contrast. Group related elements. Reduce clutter |
| **Physical** | Reduce clicks. Shorten navigation paths. Provide shortcuts. Use inline editing |
| **Navigational** | Flatten hierarchies. Combine related screens. Use tabs instead of pages |
| **Modal** | Replace dialogs with inline actions. Undo instead of confirm. Auto-save instead of manual save |

### The "Do It, Don't Ask" Principle

Whenever the system can make a reasonable decision on the user's behalf:

| Instead of | Do This |
|-----------|---------|
| "Where would you like to save?" | Save to last-used location. Let user move later |
| "What format?" | Default to most common format. Let user change if needed |
| "Are you sure you want to delete?" | Delete immediately. Provide Undo for 10 seconds |
| "Would you like to enable notifications?" | Enable sensible defaults. Let user adjust in settings |
| "Session expired. Please log in again" | Refresh token silently. Only ask for credentials when necessary |
