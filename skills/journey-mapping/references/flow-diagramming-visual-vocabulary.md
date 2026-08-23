# Flow Diagramming: JJG's Visual Vocabulary for Information Architecture

## What It Is

The Visual Vocabulary is a standardized notation system for describing the structure and flow of websites and applications, created by Jesse James Garrett in 2000. It provides a minimal, tool-independent set of symbols for documenting information architecture and interaction design at a structural level — how pages relate to each other, how users navigate between them, and where the system makes decisions on the user's behalf.

The vocabulary follows three design principles:
- **Whiteboard-compatible** — Simple enough to sketch by hand in a meeting
- **Tool-independent** — Works in any diagramming software, on paper, or on a whiteboard
- **Minimal symbol set** — Strict one-to-one correlation between concepts and symbols, so the vocabulary can be learned and applied quickly

---

## The Complete Symbol Set

### Pages and Documents

| Symbol | Name | Meaning |
|---|---|---|
| **Rectangle** | Page | A single page or screen in the experience. The basic unit of the vocabulary |
| **Stacked rectangles** (offset) | Page stack | A group of functionally identical pages generated from a single template (e.g., product detail pages, search results, user profiles) |
| **Rectangle with folded corner** | File | A downloadable or non-HTML resource — PDF, document, image, spreadsheet |
| **Stacked rectangles with folded corners** | File stack | A group of similar files (e.g., a set of PDF reports) |

**Page labeling rules:**
- Label every page with a short, descriptive name
- Use the label the user would recognize, not the internal system name
- For page stacks, label with the template name and note what varies (e.g., "Product Detail [varies by SKU]")

### Connectors and Flow

| Symbol | Name | Meaning |
|---|---|---|
| **Solid arrow** | Navigation path | A link or transition the user can follow from one page to another. The arrow indicates direction of movement |
| **Dashed arrow** | Conditional path | A navigation path that only appears under certain conditions (e.g., only for logged-in users, only after completing a step) |
| **Line without arrowhead** | Bidirectional link | Navigation that works in both directions (user can go back and forth) |

**Flow direction conventions:**
- Primary flow runs **top to bottom** or **left to right**
- Keep the dominant direction consistent within a single diagram
- Cross-links (navigation that breaks the primary flow) should be visually distinct — use curves or route around other elements rather than crossing through them

### Decision and Conditional Elements

| Symbol | Name | Meaning |
|---|---|---|
| **Diamond** | Decision point | A moment where the **user** makes a choice that determines which path they follow. Each outgoing arrow is labeled with a choice option |
| **Diamond (with different fill or border)** | Conditional selector | A moment where the **system** determines the path — not the user. The system evaluates a condition and routes accordingly (e.g., logged in vs. not logged in, mobile vs. desktop, new vs. returning) |
| **Labeled outgoing arrows** | Conditional branches | Each branch from a decision point or conditional selector is labeled with the condition or choice it represents |

**The distinction between decision points and conditional selectors is critical:**
- **Decision point** = the user chooses (e.g., "Buy now" vs. "Add to wishlist")
- **Conditional selector** = the system chooses (e.g., redirect based on user role, A/B test variant, geolocation)

In diagrams, differentiate these visually — use an open diamond for user decisions and a filled diamond for system conditions, or use distinct labels like "[USER]" and "[SYSTEM]".

### Grouping and Structure

| Symbol | Name | Meaning |
|---|---|---|
| **Dashed rectangle enclosure** | Area | A logical grouping of related pages that share a common theme, section, or navigation context (e.g., "Account Settings," "Help Center") |
| **Dashed rectangle with iteration mark** | Iterated area | An area that repeats — a section of the architecture that is replicated for different contexts (e.g., each product category has its own browse/filter/detail flow) |

**Grouping rules:**
- Areas should reflect the user's mental model of the site structure, not the organization's internal departments
- Nesting areas is permitted but avoid more than two levels deep — if you need more, the diagram needs to be split into sub-diagrams
- Every page should belong to at most one area

### Continuity Elements

| Symbol | Name | Meaning |
|---|---|---|
| **Labeled circle** | Continuation point | Connects flows that span multiple pages of a diagram. A continuation point on one page matches a continuation point with the same label on another page. The flow continues from one to the other |
| **Bracket notation** | Concurrent set | Multiple pages or screens that appear simultaneously as a result of a single action (e.g., a page opens plus a modal, or a main view and a sidebar update together) |

**Continuation point rules:**
- Use when the diagram is too large for a single page or canvas
- Label with a unique identifier (letter, number, or short name)
- Always appear in pairs — one outgoing, one incoming
- Place them at the edge of the diagram for clarity

---

## Diagram Types

The Visual Vocabulary supports several diagram types at different levels of detail:

### Site Map (High-Level Structure)

Shows the hierarchical organization of pages and sections. Focuses on **what exists and where it lives** in the architecture.

**When to use:**
- Documenting overall site structure
- Planning navigation and information groupings
- Communicating scope to stakeholders

**Conventions:**
- Home page at the top
- Primary navigation sections as first-level branches
- Page stacks for templated sections
- Areas to show logical groupings

### Task Flow (Single-User Path)

Shows the sequence of pages a user visits to complete a specific task. Focuses on **one path through the system** with no branching.

**When to use:**
- Documenting the happy path for a critical task
- Communicating a specific user scenario
- Reviewing whether a flow has unnecessary steps

**Conventions:**
- Linear, left-to-right or top-to-bottom
- Every page in the sequence connected by arrows
- No branches — this is one path, not a map of possibilities

### User Flow (Branching Paths)

Shows all possible paths a user might take through a section of the site, including decision points and conditional logic. Focuses on **choices and their consequences**.

**When to use:**
- Designing interactive sequences with user decisions
- Documenting conditional logic (login states, roles, permissions)
- Identifying all possible states and paths through a process

**Conventions:**
- Decision diamonds at every branch point
- Every branch labeled with its condition
- Dead ends and error states included — not just the happy path
- Concurrent sets where multiple things happen at once

### Wireflow (Flow + Page Layout)

Combines flow diagrams with wireframe-level page layouts. Each node in the flow is a simplified wireframe rather than a simple rectangle.

**When to use:**
- When the page layout is essential to understanding the flow (e.g., where on the page does the user click?)
- Communicating both structure and interaction to developers
- Reviewing flows where spatial layout affects decisions

**Conventions:**
- Keep wireframes low-fidelity — just enough to show layout zones and key elements
- Highlight the interactive element that triggers navigation to the next step
- Don't mix wireflow detail with site map breadth — wireflows are for focused sequences

---

## When to Use Flow Diagrams Alongside Alignment Diagrams

Flow diagrams and alignment diagrams answer fundamentally different questions:

| Question | Use |
|---|---|
| "What does the user **experience** across our service?" | Alignment diagram (journey map, blueprint, experience map) |
| "How is the site/app **structured** and how do users **navigate** it?" | Flow diagram (site map, user flow, task flow) |
| "Where does the user **decide** or get **routed** during a digital interaction?" | Flow diagram with decision points and conditional selectors |

They are complementary, not competing. Common patterns for using them together:

### Pattern 1: Touchpoint Zoom-In

A journey map identifies a digital touchpoint as a pain point (e.g., "Onboarding flow is confusing"). Create a user flow diagram of that specific touchpoint to diagnose *where* in the interaction the confusion occurs — which screens, which decision points, which dead ends.

**Journey map** reveals *that* there's a problem and *how it feels*.
**Flow diagram** reveals *where* the structural problem is and *what to redesign*.

### Pattern 2: Blueprint Backstage Detail

A service blueprint shows system actions in the backstage and support process lanes. When these involve complex conditional logic (e.g., routing a support ticket based on issue type, user tier, and agent availability), a flow diagram with conditional selectors documents the decision logic more precisely than a blueprint annotation can.

**Blueprint** shows *that* a decision happens and *which lane it's in*.
**Flow diagram** shows *what the decision logic is* and *all possible outcomes*.

### Pattern 3: Experience-to-Architecture Bridge

An experience map reveals the broad activity and pain points. A site map shows how the current architecture is organized. Overlaying them reveals mismatches — where the architecture doesn't match the user's mental model of the activity. Phases in the experience map should correspond to areas in the site map. When they don't, that's a structural problem.

### Pattern 4: Ecosystem Flow Detail

An ecosystem model shows entities and value flows at a high level. When a specific flow between entities involves conditional routing, multiple steps, or concurrent actions, a flow diagram documents the detail. This is especially useful for platform businesses where the flow between user types involves system-mediated decisions.

---

## Constructing a Flow Diagram: Process

### Step 1: Define Scope

- **What task or section?** — Don't diagram the entire site at full detail. Pick a scope: one task, one section, or a high-level overview
- **What level of detail?** — Site map (structure only), task flow (single path), user flow (all paths), or wireflow (flow + layout)?
- **Who is the audience?** — Stakeholders need site maps; designers need user flows; developers need wireflows

### Step 2: Inventory the Pages

List every page or screen involved. For each page:
- Name it from the user's perspective
- Note whether it's a unique page or part of a page stack (template)
- Note any files associated with it

### Step 3: Map the Connections

For each page, document:
- Where can the user go from here? (outgoing arrows)
- Are any paths conditional? (dashed arrows, decision points)
- Does the system make any routing decisions? (conditional selectors)
- Do any actions trigger concurrent results? (concurrent sets)

### Step 4: Group into Areas

Look for clusters of related pages:
- Do they share a navigation context?
- Would the user think of them as "the same section"?
- Draw area boundaries around them

### Step 5: Annotate

Add annotations that connect the flow diagram to the broader experience context:
- Flag pages that correspond to pain points from the journey map
- Mark decision points that cause user confusion (from research)
- Note pages with high drop-off rates (from analytics)
- Highlight where conditional selectors create different experiences for different user segments

### Step 6: Validate

- Walk through the diagram with the development team: "Is this how it actually works?"
- Walk through with a designer: "Is this how it *should* work?"
- Cross-reference with the journey map: "Does this flow support or undermine the experience we're trying to create?"

---

## Common Mistakes

| Mistake | Why It Fails | Instead |
|---|---|---|
| Diagramming every page at full detail | Unreadable, takes forever to maintain | Use page stacks for templated sections; diagram detail only where it matters |
| Mixing user decisions and system decisions | Obscures who is in control at each point | Use distinct symbols — open vs. filled diamonds, or explicit labels |
| Omitting error states and dead ends | Happy-path-only diagrams miss the most important design problems | Include every path the user could end up on, including errors and edge cases |
| No connection to research data | Produces a technically accurate but experientially meaningless diagram | Annotate with journey map findings, analytics, and usability data |
| Using the flow diagram as the only artifact | Flow diagrams don't capture emotion, motivation, or experience quality | Pair with alignment diagrams — the flow shows structure, the journey map shows experience |
| Inconsistent flow direction | Reader can't follow the diagram | Pick one dominant direction (top-to-bottom or left-to-right) and stick with it |

---

## Source

Jesse James Garrett, *A Visual Vocabulary for Describing Information Architecture and Interaction Design*, 2000 (updated 2002). Originally published at jjg.net/ia/visvocab/. The vocabulary has been translated into multiple languages and adopted as a de facto standard for site architecture documentation.

Garrett also authored *The Elements of User Experience* (2002, 2nd ed. 2010), which places information architecture and interaction design within a five-plane model: Strategy, Scope, Structure, Skeleton, and Surface. The Visual Vocabulary operates primarily at the **Structure** and **Skeleton** planes — defining the conceptual structure of the site and the concrete arrangement of interface elements.