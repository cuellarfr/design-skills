# Interaction Design Principles

Core principles from established interaction design theory. These frameworks go beyond individual patterns to evaluate the overall quality of an interface's behavior.

---

## Product Posture

Every product has a behavioral stance — how much attention it demands and how it presents itself to users. Mismatched posture is one of the most common and least-diagnosed design failures.

### Posture Types

| Posture | User Attention | Duration | Examples |
|---|---|---|---|
| **Sovereign** | Full, sustained attention | Hours per session | Email clients, IDEs, design tools, spreadsheets |
| **Transient** | Brief, focused attention | Seconds to minutes | Calculators, settings panels, search overlays |
| **Daemonic** | No attention (background) | Continuous | Backup services, sync engines, print spoolers |

### Design Implications by Posture

**Sovereign posture (full-screen, long-session apps):**
- Target perpetual intermediates (not beginners)
- Be generous with screen real estate — no other app competes
- Use muted visual style (users stare at it for hours)
- Provide rich visual feedback and direct manipulation
- Support keyboard shortcuts and accelerators
- Design for documents and workspaces, not wizards

**Transient posture (come-and-go tools):**
- Must be immediately obvious — users won't invest time learning
- Bright, clear visual style with high contrast
- Keep it simple — minimal features visible
- Remember user choices between sessions
- Fast in, fast out — no onboarding flow

**Daemonic posture (invisible background processes):**
- Normally no UI at all
- Configuration via a transient settings panel
- Surface only when something needs human attention
- Provide direct access when the daemon blocks a user task
- Status should be available but not intrusive (system tray, status bar)

### Posture Diagnosis

Ask these questions during critique:

| Question | If Answer is Wrong |
|---|---|
| How long do users typically spend with this interface? | Posture may be mismatched to session length |
| Is the visual density appropriate for session duration? | Sovereign apps need density; transient apps need clarity |
| Does the onboarding match the posture? | Sovereign: teach over time. Transient: be self-evident |
| Are keyboard shortcuts available for sovereign apps? | Power users will be frustrated without them |
| Can transient tools be dismissed instantly? | If not, they're blocking the user's actual task |

---

## Perpetual Intermediates

Most users are intermediates, and they stay that way. Design for them.

### The Three Audiences

| Level | % of Users | Behavior | What They Need |
|---|---|---|---|
| **Beginners** | ~10% (temporary) | Cautious, reading everything, fear of breaking things | Quick path to intermediacy, not dumbed-down interface |
| **Intermediates** | ~80% (permanent) | Use a working set of features, comfortable but not exploring | Optimized access to their working set, discoverable depth |
| **Experts** | ~10% (dedicated) | Know shortcuts, customize heavily, push limits | No obstacles, full power, customization |

### Design Strategies

**For beginners (goal: move them to intermediate fast):**
- Provide multiple command modalities: pedagogic (menu items with labels) + immediate (toolbar buttons) + invisible (keyboard shortcuts)
- Use memorization vectors: show the shortcut next to the menu item so users naturally learn it
- Guided tours for complex features, but always skippable
- Blank slate / empty states that teach by doing
- Don't dumb down the interface — beginners become intermediates quickly

**For perpetual intermediates (goal: keep them productive):**
- Organize by frequency of use — most-used features most accessible
- Use interface inflection: frequently used functions in toolbars/palettes, infrequent ones in menus
- Progressive disclosure for advanced options
- Sticky preferences — remember customizations across sessions
- Contextual help available but not intrusive

**For experts (goal: don't block them):**
- Keyboard shortcuts for everything common
- Customizable interface (toolbars, layouts, macros)
- No unnecessary confirmation dialogs
- Commensurate effort: complex features can have complex controls if the reward justifies it
- Don't force experts through beginner flows

### Working Set Concept

Users memorize a personal subset of features (their "working set") through repetition. Two implications:

1. **The working set is idiosyncratic** — different users memorize different features. Design must support varied working sets.
2. **The working set is small relative to total features** — even experts use maybe 30% of features regularly. The rest should be discoverable but not cluttering the main interface.

---

## The Four Types of User Work

Every interaction imposes work on the user. Good design minimizes total work across all four types.

### Work Types

| Type | Description | Design Response |
|---|---|---|
| **Cognitive work** | Understanding behaviors, text, structures | Clear labeling, consistent patterns, match mental models |
| **Memory work** | Remembering commands, locations, passwords, prior states | Recognition over recall, persistent state, smart defaults |
| **Visual work** | Finding things on screen, decoding layout, distinguishing elements | Visual hierarchy, grouping, contrast, whitespace |
| **Physical work** | Clicks, keystrokes, mouse travel, mode switching | Fitts's Law, keyboard shortcuts, reduce navigation |

### Excise: Work That Doesn't Serve Goals

Excise is work the user must do that doesn't directly advance their goal. It's the tax the interface charges for using it.

**Navigational excise** (most common, most damaging):
- Navigation across multiple screens/views/pages
- Navigation between panes within a screen
- Navigation between tools and menus
- Navigation of information (scrolling, searching for content)

**Fix:** Reduce places to go. Provide signposts and overviews. Map controls to functions properly. Avoid unnecessary hierarchy. Put related functions on the same screen.

**Modal excise:**
- Unnecessary error messages that interrupt flow
- Confirmation dialogs for reversible actions
- Making users "ask permission" before editing
- Forcing users to close one thing before opening another

**Fix:** Use modeless feedback (inline, non-blocking). Enable undo instead of confirm dialogs. Allow input wherever there is output (inline editing).

**Stylistic excise:**
- Decoding which elements are clickable vs. decorative
- Figuring out where to start reading on a screen
- Distinguishing between visually similar elements

**Fix:** Clear affordances. Consistent interactive element styling. Visual hierarchy that guides the eye.

**Skeuomorphic excise:**
- Forcing digital interactions into physical-world metaphors that don't apply
- File system navigation mimicking physical filing cabinets
- "Save" as a manual action when autosave is possible

**Fix:** Use idioms, not metaphors. Design for what digital can do, not what physical had to do.

### Excise Audit Checklist

Use during design critique to identify unnecessary work:

- [ ] Can the user complete the primary task without leaving this screen?
- [ ] Are there unnecessary steps between intention and action?
- [ ] Does the user have to remember information from a previous screen?
- [ ] Are there confirmation dialogs for actions that could be undone instead?
- [ ] Does the user have to navigate to a settings page to do something that should be inline?
- [ ] Are there places where the system could fill in information the user is being asked to provide?
- [ ] Does the user need to format data in a specific way the system could handle?
- [ ] Are there places where the user is doing work the computer should do (calculating, sorting, comparing)?

---

## Orchestration and Flow

When all interface elements work together coherently, the interface becomes transparent — users focus on their work, not on the tool.

### Flow State

Flow is the state of complete concentration where users lose awareness of the tool and focus entirely on their task. Design that supports flow:

- Is transparent — the interface doesn't call attention to itself
- Provides immediate feedback for all actions
- Matches the user's mental model of the task
- Minimizes interruptions and mode changes
- Maintains context during transitions

### Harmonious Interaction Principles

| Principle | What It Means | Violation Signal |
|---|---|---|
| **Follow mental models** | Structure matches how users think about the task, not how the code works | Organization reflects database schema or API structure |
| **Less is more** | Every visible element earns its place | Decorative elements compete with functional ones |
| **Direct over discuss** | Users manipulate objects, not fill in dialog boxes | Too many forms and settings; not enough direct interaction |
| **Choices over questions** | Present options rather than asking open-ended questions | Text inputs where dropdowns/toggles would work |
| **Tools close at hand** | Frequently used functions are immediately accessible | Common actions buried in menus or subpages |
| **Modeless feedback** | Status and feedback shown without interrupting flow | Modal alerts for non-critical information |
| **Design for the probable** | Optimize for common cases; accommodate edge cases | Equal prominence for 80% use case and 2% edge case |
| **Contextualize information** | Data shown in context of where it's needed | Information on one screen needed to make decisions on another |
| **Reflect status** | Object and system state is always visible | No indication of mode, selection, or progress |
| **Hide the ejector seat** | Dangerous/rare functions are less accessible, not less available | Destructive actions as prominent as common actions |

### Responsiveness Thresholds

| Time | User Perception | Design Response |
|---|---|---|
| **< 100ms** | Instantaneous | No feedback needed |
| **100ms – 1s** | Responsive but noticeable | Subtle loading indicator (spinner, pulse) |
| **1s – 10s** | System is slow | Progress bar or skeleton screen; keep user informed |
| **> 10s** | Attention lost | Background process + notification on completion; don't block the user |

### Motion and Transition Guidelines

Animation should:
- Focus attention on the right place after a state change
- Show relationships between objects and their actions
- Maintain spatial context during transitions between views
- Provide perception of progress (progress bars, spinners)
- Be short (200-500ms), meaningful, and natural

Animation should NOT:
- Delay the user from reaching their goal
- Be decorative without functional purpose
- Be so fast it's missed or so slow it's annoying
- Create motion sickness (large-scale parallax, constant movement)

---

## Interface Paradigms

Understanding how users learn interfaces helps evaluate whether a design is learnable.

### Three Paradigms

| Paradigm | How Users Learn | Strengths | Weaknesses |
|---|---|---|---|
| **Implementation-centric** | Users must understand how the system works internally | Powerful for developers | Unusable for non-technical users |
| **Metaphoric** | Users map interface to real-world objects they know | Instant recognition for good matches | Breaks down when metaphor doesn't fit; doesn't scale |
| **Idiomatic** | Users learn interface conventions through use | Infinite vocabulary; scales well; most of modern UI | Requires initial learning; must be consistent |

### Implications for Critique

- **Most modern UI is idiomatic** — labeled buttons, navigation bars, dropdowns, modals are idioms users learn once and apply everywhere
- **Good idioms are learned once** — if users need to re-learn your interface on every visit, your idioms are too unusual or inconsistent
- **Don't rely on metaphors** — a shopping "cart" metaphor works; a "desktop" metaphor for file management arguably doesn't anymore
- **Never expose implementation** — if users need to understand databases, APIs, or file systems to use the product, the abstraction has failed

### Direct Manipulation and Affordances

**Direct manipulation** means users act on objects directly rather than issuing commands about them. Three requirements:
1. Visual representation of objects users care about
2. Visible mechanisms for acting on them (handles, buttons, gestures)
3. Immediately visible results

**Pliancy** is the visual communication that an element can be manipulated:
- Static affordances: the element looks interactive by default (button shape, underlined link)
- Dynamic affordances: the element changes on hover/focus (color change, cursor change)
- Cursor affordances: the cursor changes over interactive areas (pointer, resize handles)

**Critique checkpoint:** For every interactive element, ask: "Is it visually obvious that this can be interacted with, and how?" If the answer is no, the element needs stronger affordances.

---

## Designing for Different Needs

### Command Modalities

The same function should be accessible through multiple paths suited to different expertise levels:

| Modality | Expertise Level | Example | Learning Path |
|---|---|---|---|
| **Pedagogic** | Beginner | Menu item with full label | User reads and clicks |
| **Immediate** | Intermediate | Toolbar button with icon + tooltip | User learns through repeated menu use |
| **Invisible** | Expert | Keyboard shortcut | Shown next to menu item (memorization vector) |

The **memorization vector** is key: showing the keyboard shortcut next to the menu item creates a natural path from beginner to expert without separate training.

### Contextual Help Hierarchy

| Help Type | When to Use | Example |
|---|---|---|
| **Inline hints** | First encounter with a feature | Placeholder text, tooltip on hover |
| **Guided overlay** | First use of a complex product | Step-by-step coachmarks |
| **Templates** | First content creation | "Start from a template" gallery |
| **Contextual help** | Specific confusion during use | "?" icon next to complex fields |
| **Documentation** | Intermediate users expanding knowledge | Searchable help center |

### Customization Spectrum

| Level | Who Uses It | Examples |
|---|---|---|
| **Personalization** | Everyone | Avatar, theme, display name |
| **Configuration** | Intermediates | Default view, notification preferences, pinned items |
| **Customization** | Experts | Custom toolbars, macros, keyboard remapping |
| **Extension** | Developers | Plugins, APIs, scripting |

**Critique checkpoint:** Is the level of customization appropriate for the audience? A consumer app with developer-level configuration is overwhelming. A professional tool without keyboard shortcuts is frustrating.
