# Design-to-Development Handoff

Deep reference for preparing, delivering, and following through on design handoff. The goal: engineers should never have to guess.

---

## Handoff Preparation

### Pre-Handoff Checklist

Before scheduling a handoff session, every design must pass this checklist:

| Category | Check | Status |
|----------|-------|--------|
| **Completeness** | All screens in the flow are designed (not just the happy path) | [ ] |
| **States** | Every interactive element has all states: default, hover, focus, active, disabled, loading, error, success, empty | [ ] |
| **Responsive** | Designs exist for mobile (320px), tablet (768px), and desktop (1440px) at minimum | [ ] |
| **Content** | Real copy is used — no lorem ipsum. Character limits documented | [ ] |
| **Tokens** | All values reference design tokens, not raw hex/px values | [ ] |
| **Components** | Design uses existing design system components where possible. New components are clearly marked | [ ] |
| **Accessibility** | Focus order documented. ARIA roles specified. Contrast verified. Touch targets 44px+ | [ ] |
| **Edge cases** | Long strings, empty states, error recovery, max/min data, permissions | [ ] |
| **Assets** | Icons exported as SVG. Images have alt text. Animations have specs | [ ] |
| **Flows** | User flows show all paths including error, back navigation, and exit points | [ ] |
| **Annotations** | Behavior notes on every frame explaining what's not visible in the static design | [ ] |

### Annotation Standards

Annotations explain what the static design can't show. Every handoff frame should include notes for:

**Behavior annotations:**
- What happens on click/tap (navigation, state change, API call)
- Keyboard interaction (Tab, Enter, Escape, Arrow keys)
- What triggers loading states and how long they persist
- Transition and animation specifications
- Scroll behavior (sticky headers, infinite scroll, pagination)

**Content annotations:**
- Maximum character counts for text fields
- Truncation rules (ellipsis, word break, fade)
- Dynamic content sources (what comes from the API vs. what's static)
- Localization notes (text expansion for longer languages — German is ~30% longer than English)
- Pluralization rules ("1 item" vs. "2 items")

**Layout annotations:**
- Container behavior (fixed width, fluid, max-width)
- What happens when content exceeds the container
- Responsive breakpoint behavior (reflow, stack, hide, change)
- Spacing tokens used (not pixel values)

---

## Handoff Documentation Formats

### Screen-Level Spec

For each screen in a flow:

```
Screen: [Screen Name]
Flow: [Flow Name] > Step [#]
Figma: [Link to frame]

## Layout
- Container: max-width [token], centered
- Grid: [columns] at [breakpoint]
- Spacing: [tokens used]

## Interactive Elements
[For each element:]
- Element: [Name]
- Component: [Design system component name]
- States: [List all states with links to frames]
- Behavior: [What it does on interaction]
- Keyboard: [Keyboard interaction]
- ARIA: [Role, label, announcements]

## Content
- [Field]: [Copy] (max [n] characters, truncate with ellipsis)
- [Field]: [Dynamic — from API endpoint [name]]

## Responsive
- Desktop (1440px+): [Description]
- Tablet (768px-1439px): [Description]
- Mobile (320px-767px): [Description]

## Edge Cases
- Empty state: [What shows when there's no data]
- Error state: [What shows when the request fails]
- Loading state: [What shows during data fetch]
- Long content: [How overflow is handled]
```

### Component-Level Spec

For new or modified components:

```
Component: [Name]
Design system: [New / Modification of existing [name]]
Figma: [Link to component frame]

## Props / Variants
| Prop | Type | Default | Options |
|------|------|---------|---------|
| variant | enum | "primary" | primary, secondary, tertiary |
| size | enum | "medium" | small, medium, large |
| disabled | boolean | false | true, false |
| loading | boolean | false | true, false |

## States
[Frame links for each state]

## Tokens Used
- Background: [token]
- Text: [token]
- Border: [token]
- Spacing: [token]
- Border-radius: [token]
- Typography: [token]

## Behavior
- Click: [What happens]
- Keyboard: [What keys trigger what]
- Focus: [Focus ring style, focus order in parent]

## Accessibility
- Role: [ARIA role]
- Label: [aria-label or aria-labelledby]
- Announcements: [What screen reader announces on state change]
```

### Flow-Level Spec

For multi-step flows:

```
Flow: [Name]
Entry point: [Where the user comes from]
Exit points: [Where the user can go]
Figma: [Link to flow page]

## Steps
1. [Screen name] → [Action] → [Next screen]
2. [Screen name] → [Action] → [Next screen]
   ↳ Error path: [Screen name] → [Recovery action] → [Resume point]
3. ...

## State Management
- [What data is collected at each step]
- [What data persists if the user navigates back]
- [What happens if the user abandons mid-flow]

## Analytics Events
| Step | Event | Properties |
|------|-------|-----------|
| Step 1 viewed | flow_step_viewed | flow_name, step_number |
| Step 1 completed | flow_step_completed | flow_name, step_number, duration |
| Flow completed | flow_completed | flow_name, total_duration |
| Flow abandoned | flow_abandoned | flow_name, last_step, reason |
```

---

## Handoff Tools and Workflows

### Figma-Based Handoff

| Feature | How to Use It |
|---------|--------------|
| **Dev Mode** | Engineers toggle to Dev Mode to inspect spacing, properties, code snippets |
| **Component properties** | Component props in Figma map to code props — name them identically |
| **Auto layout** | Use auto layout everywhere — it translates directly to flexbox/CSS |
| **Design tokens** | Use token names in styles (via Tokens Studio or similar) so engineers see `spacing-md`, not `16px` |
| **Sections** | Organize frames into sections: "Happy Path," "Error States," "Responsive," "Components" |
| **Annotations** | Use Figma's built-in annotation feature or a plugin for behavior notes |
| **Links** | Link between frames to show flow connections |
| **Version history** | Use named versions at each handoff milestone |

### Storybook Integration

For teams using Storybook:

1. **Component spec in Figma** → maps to a Storybook story
2. **Each variant** in the design → maps to a story variant
3. **Each state** → maps to a story with that state active
4. **Design QA** compares Storybook rendering against Figma frame side-by-side
5. **Figma links** embedded in Storybook story descriptions for traceability

### Code Connect (Figma)

For mature teams, Code Connect links Figma components directly to code:

- Designer selects a component in Figma → sees the actual code implementation
- Engineer inspects a design → sees which code component to use and how
- Reduces spec ambiguity to near zero for existing components
- New components still need full specs

---

## Handoff Workflow by Team Size

### Small Team (1 designer, 2-5 engineers)

| Aspect | Approach |
|--------|---------|
| **Tool** | Figma with comments and annotations |
| **Process** | Designer shares Figma link in the ticket. 15-min walkthrough call. Engineers ask questions in Figma comments |
| **Cadence** | Per story, as they're picked up |
| **QA** | Designer reviews PR in staging or Storybook |
| **Overhead** | Low — minimal documentation, high-bandwidth conversation |

### Medium Team (2-3 designers, 5-15 engineers)

| Aspect | Approach |
|--------|---------|
| **Tool** | Figma with Dev Mode, design system in Storybook |
| **Process** | Weekly handoff sessions. Screen-level specs for complex features. Component specs for new components |
| **Cadence** | Batch handoff at sprint planning. Ad-hoc for questions |
| **QA** | Dedicated design QA time in each sprint |
| **Overhead** | Medium — some documentation, structured sessions |

### Large Team (4+ designers, 15+ engineers)

| Aspect | Approach |
|--------|---------|
| **Tool** | Figma with Dev Mode + Code Connect, design system with full Storybook, token pipeline |
| **Process** | Formal handoff docs per feature. Component specs mandatory. Flow specs for multi-step features |
| **Cadence** | Design works 1 sprint ahead. Handoff at sprint boundaries |
| **QA** | Design QA as a formal phase in the pipeline, with QA engineer support |
| **Overhead** | Higher — more documentation, but shared language reduces ambiguity |

---

## Handling Handoff Conflicts

### Designer-Engineer Disagreements

| Conflict | Resolution |
|----------|-----------|
| "This is too hard to build" | Discuss alternatives. Design proposes 3 options at different complexity levels. Team chooses based on sprint capacity |
| "This doesn't match the spec" | Reference the spec. If the spec was ambiguous, acknowledge and clarify — don't blame. Update the spec |
| "We need to cut scope" | Designer identifies which parts can be deferred without breaking the experience. Never cut error states or accessibility |
| "The design changed after handoff" | All post-handoff changes go through a change request: what changed, why, impact on engineering work |
| "It works differently on [platform]" | Document platform-specific behavior in the spec. Don't assume web behavior translates to mobile |

### Post-Handoff Design Changes

Changes after handoff are expensive. Minimize them by:

1. **Getting engineering input early** — before handoff, not after
2. **Using a change request process:**
   ```
   Change request:
   - What changed: [Description]
   - Why: [New information, user feedback, stakeholder request]
   - Impact: [Which stories/components are affected]
   - Priority: [Must-have for this release / Can wait for next sprint]
   ```
3. **Tracking change frequency** — if changes are frequent, the process upstream is broken (discovery, critique, or review)
