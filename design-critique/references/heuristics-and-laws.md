# Heuristics and UX Laws: Detailed Reference

## Part 1: Nielsen's 10 Heuristics — Expanded

### H1: Visibility of System Status

The system should always keep users informed about what is going on, through appropriate feedback within reasonable time.

**What to look for:**
- After every user action, is there visual feedback?
- Do loading states show progress (determinate) or activity (indeterminate)?
- Is the currently selected/active item highlighted?
- Do forms show which step the user is on?
- After submission, is there a clear success or failure message?
- Does the system show when it's processing?

**Common violations:**
- Button clicked but nothing visible happens for 2+ seconds
- Form submitted but no confirmation
- Active navigation item not highlighted
- File uploading with no progress indicator
- Background task running with no notification

**Benchmark (Doherty Threshold):** System feedback should appear within 400ms. If an action takes longer, show a loading state immediately.

---

### H2: Match Between System and Real World

The system should speak the user's language, with words, phrases, and concepts familiar to the user, rather than system-oriented terms.

**What to look for:**
- Does the interface use words users would use?
- Are icons recognizable without labels?
- Is content ordered in a logical, natural way?
- Do metaphors match real-world equivalents?
- Are dates, currencies, and formats localized?

**Common violations:**
- Technical jargon: "Null reference exception" instead of "Something went wrong"
- Internal terminology: "SKU" when users say "product"
- Alphabetical ordering when users think in categories
- Unfamiliar icons without text labels
- Developer-facing field names: "fname" instead of "First name"

**Test:** Show labels to 5 users and ask what they'd expect to find. If 3+ guess wrong, rename it.

---

### H3: User Control and Freedom

Users often choose system functions by mistake and will need a clearly marked "emergency exit" to leave the unwanted state without having to go through an extended dialogue.

**What to look for:**
- Can users undo their last action?
- Can users cancel mid-flow and return to where they were?
- Can users go back to the previous step?
- Can users close/dismiss overlays and modals?
- Can users edit what they've already submitted?

**Common violations:**
- No undo after deleting an item
- Wizard with no "Back" button
- Modal with no close button or Escape support
- Confirmation step with no "Edit" option
- Auto-advancing carousel with no manual control

---

### H4: Consistency and Standards

Users should not have to wonder whether different words, situations, or actions mean the same thing. Follow platform conventions.

**What to look for:**

**Internal consistency (within the product):**
- Same action, same label everywhere ("Delete" not sometimes "Remove")
- Same component, same behavior everywhere
- Same visual treatment for same element type
- Same placement for recurring elements (search, profile, notifications)

**External consistency (with the ecosystem):**
- Standard icons (gear = settings, magnifying glass = search)
- Standard patterns (logo top-left links to home, swipe to delete on mobile)
- Platform conventions (iOS back button top-left, Android bottom navigation)
- Web conventions (blue underlined text = link, asterisk = required)

**Common violations:**
- "Save" in one place, "Submit" in another for the same action
- Different icon styles mixed on the same page
- Non-standard gesture for a standard action
- Primary button placement changing between screens

---

### H5: Error Prevention

Even better than good error messages is a careful design which prevents a problem from occurring in the first place.

**Two types of errors to prevent:**

**Slips** (unintentional actions):
- Confirmation dialog before destructive action ("Are you sure you want to delete?")
- Undo instead of confirm (Gmail's "Undo Send")
- Disabled buttons when required fields are empty
- Smart defaults that pre-fill likely values
- Physical separation of destructive and constructive actions

**Mistakes** (wrong mental model):
- Constraints that make wrong input impossible (date picker vs. text field)
- Inline validation before submission
- Clear labels that prevent misunderstanding
- Examples showing expected format
- Preview before committing

---

### H6: Recognition Rather Than Recall

Minimize the user's memory load by making objects, actions, and options visible. The user should not have to remember information from one part of the dialogue to another.

**What to look for:**
- Are all available options visible (or easily accessible)?
- Does the system show previously entered data when editing?
- Are recently used items available for quick access?
- Are instructions visible at the point of need?
- Does the interface carry forward context from previous steps?

**Common violations:**
- Requiring users to remember a code or ID from a previous screen
- Filter settings that reset when returning to a list
- "Refer to the documentation" instead of inline help
- Search without recent/suggested queries
- Form that doesn't remember user's previous entries

---

### H7: Flexibility and Efficiency of Use

Accelerators — unseen by the novice user — may often speed up the interaction for the expert user such that the system can cater to both inexperienced and experienced users.

**What to look for:**
- Are keyboard shortcuts available for frequent actions?
- Can users customize or personalize their workspace?
- Are there shortcuts for power users (bulk actions, quick filters)?
- Is there a balance between guided flow (novice) and direct access (expert)?
- Can users set defaults and preferences?

**Implementation spectrum:**
- **Novice:** Step-by-step wizards, tooltips, guided flows
- **Intermediate:** Shortcuts visible, direct navigation, saved preferences
- **Expert:** Keyboard shortcuts, command palette, customizable workflows, API access

---

### H8: Aesthetic and Minimalist Design

Dialogues should not contain information which is irrelevant or rarely needed. Every extra unit of information in a dialogue competes with the relevant units of information and diminishes their relative visibility.

**What to look for:**
- Does every element serve a purpose?
- Is information density appropriate for the context?
- Is the visual design supporting or competing with the content?
- Are decorative elements adding value or just noise?
- Is the most important information the most visually prominent?

**The Krug test:** For every element, ask "Can I remove this?" If the answer is yes, remove it. Then ask again.

**Red flags:**
- More than 3 font sizes on a single screen
- More than 3 primary colors
- Competing calls to action (multiple buttons vying for attention)
- Marketing copy in task-oriented flows
- Decorative images that don't convey information

---

### H9: Help Users Recognize, Diagnose, and Recover from Errors

Error messages should be expressed in plain language (no codes), precisely indicate the problem, and constructively suggest a solution.

**Good error message formula:**
1. **What happened** — in plain language
2. **Why** — if it helps the user understand
3. **How to fix it** — specific action to take
4. **One-click recovery** — button/link to fix it directly

**Examples:**

| Bad | Good |
|---|---|
| "Error 500" | "Something went wrong on our end. Please try again in a few minutes." |
| "Invalid input" | "Email address needs an @ symbol — for example, name@company.com" |
| "Forbidden" | "You don't have permission to view this page. Contact your admin to request access." |
| "Network error" | "Couldn't save — check your internet connection and try again." |

---

### H10: Help and Documentation

Even though it is better if the system can be used without documentation, it may be necessary to provide help and documentation. Any such information should be easy to search, focused on the user's task, list concrete steps to be carried out, and not be too large.

**What to look for:**
- Is contextual help available at the point of need?
- Is the help searchable?
- Is it task-oriented (not feature-oriented)?
- Are there concrete examples?
- Is it accessible without leaving the current flow?

**Hierarchy of help:**
1. **Self-evident design** — no help needed (best)
2. **Inline hints** — tooltips, placeholder examples, helper text
3. **Contextual help** — ? icon that expands relevant help
4. **Guided tour** — step-by-step onboarding for new users
5. **Documentation** — searchable knowledge base (last resort)

---

## Part 2: 27 UX Laws — Organized by Design Domain

### Perception and Visual Processing

| Law | Core Principle | Design Application |
|---|---|---|
| **Law of Proximity** | Near things are grouped | Space related items close; separate unrelated items |
| **Law of Similarity** | Similar things are grouped | Style same-function elements identically |
| **Law of Common Region** | Bordered things are grouped | Use containers, cards, backgrounds for grouping |
| **Law of Uniform Connectedness** | Connected things are related | Lines, arrows, shared color show relationship |
| **Law of Prägnanz** | Simple interpretation wins | Reduce ambiguity; make the simplest reading the correct one |
| **Selective Attention** | We filter out irrelevant stimuli | Guide attention; avoid banner-blindness zones; highlight changes |

### Cognition and Memory

| Law | Core Principle | Design Application |
|---|---|---|
| **Cognitive Load** | Mental capacity is finite | Reduce extraneous load; chunk information; provide defaults |
| **Miller's Law** | Working memory ≈ 7±2 items | Group into chunks of 3-5; don't present 10+ ungrouped options |
| **Working Memory** | Fades in 20-30 seconds | Don't require cross-screen memorization; carry data forward |
| **Mental Model** | Users expect what they already know | Match structure to user expectations, not org chart |
| **Cognitive Bias** | Decisions are not rational | Account for anchoring, framing, confirmation bias in design |

### Decision Making

| Law | Core Principle | Design Application |
|---|---|---|
| **Hick's Law** | More options = slower decisions | Limit visible choices; use progressive disclosure |
| **Choice Overload** | Too many options paralyzes | Filter and sort first; recommend defaults; enable comparison |
| **Occam's Razor** | Simplest solution wins | Remove until you can remove no more |
| **Paradox of Active User** | Users skip instructions | Design to be self-evident; provide guidance in-context |

### Interaction and Timing

| Law | Core Principle | Design Application |
|---|---|---|
| **Fitts's Law** | Size and distance affect targeting | Large targets, close to cursor; corners/edges on desktop |
| **Doherty Threshold** | <400ms feedback feels instant | Show immediate feedback; use skeleton screens; optimistic UI |
| **Parkinson's Law** | Tasks expand to fill time | Set expectations; autofill; reduce form length |
| **Postel's Law** | Accept variable input | Forgive formatting; accept synonyms; handle edge cases |
| **Tesler's Law** | Complexity must live somewhere | Push complexity to the system; automate where possible |

### Motivation and Behavior

| Law | Core Principle | Design Application |
|---|---|---|
| **Goal-Gradient Effect** | Motivation increases near completion | Show progress; give head start; indicate remaining steps |
| **Zeigarnik Effect** | Incomplete tasks are remembered | Show what's incomplete; use progress indicators |
| **Peak-End Rule** | Peaks and endings define memory | Design highlights and strong finishes; avoid frustrating endings |
| **Flow** | Balance challenge and skill | Match difficulty to user level; minimize interruptions |
| **Aesthetic-Usability Effect** | Beauty = perceived usability | Invest in visual quality — but still test usability |

### Familiarity and Recall

| Law | Core Principle | Design Application |
|---|---|---|
| **Jakob's Law** | Users prefer what they know | Use conventions; innovate only with evidence |
| **Von Restorff Effect** | Different things are remembered | Make the key element visually distinct |
| **Serial Position Effect** | First and last items are remembered | Place important items at start and end of lists |

---

## Conducting a Heuristic Evaluation

### Process

1. **Recruit 3-5 evaluators** — Research shows 3-5 evaluators find ~75% of usability problems. More evaluators have diminishing returns.

2. **Brief evaluators** — Provide persona, scenario, and task context. Evaluators should know who uses this and what they're trying to do.

3. **Independent evaluation** — Each evaluator reviews independently. Going through the interface at least twice: once to get familiar, once to evaluate.

4. **Score each finding** — Use the 0-4 severity scale (see SKILL.md).

5. **Aggregate and deduplicate** — Combine all evaluators' findings. Average severity scores. Flag issues found by multiple evaluators.

6. **Prioritize** — Sort by severity. Group by heuristic to spot patterns (if 5 issues are H4/Consistency, the design system needs work).

### Scoring Agreement

When multiple evaluators score the same issue differently, use the median score. If there's strong disagreement (4 vs. 1), discuss — one evaluator may have context others don't.

### Output

Use `templates/heuristic-evaluation-template.md` for the full scorecard format.
