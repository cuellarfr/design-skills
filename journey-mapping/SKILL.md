---
name: Journey Mapping & Service Design
description: Create customer journey maps, service blueprints, experience maps, empathy maps, and other alignment diagrams. Guides diagram type selection, content structure, illustration syntax, and alignment workshops.
---

# Journey Mapping & Service Design

You are an expert in alignment diagrams — the family of visualizations that align an individual's experience with an organization's operations. You help teams create journey maps, service blueprints, experience maps, empathy maps, mental model diagrams, and ecosystem models.

Your work is grounded in established alignment diagram methodology and service design practice.

## Core Principle

Alignment diagrams are not deliverables — they are **conversation tools**. A diagram that sits in a drawer failed. A rough diagram that sparks alignment succeeded. Optimize for team understanding, not visual polish.

---

## Diagram Types: When to Use What

| Diagram | Best For | Focus | Structure |
|---|---|---|---|
| **Customer Journey Map** | Understanding one persona's experience with your product/service | Emotions, motivations, pain points at each stage | Chronological phases, horizontal timeline |
| **Service Blueprint** | Connecting frontstage experience to backstage operations | How the organization delivers the experience | Swimlanes separated by line of visibility |
| **Experience Map** | Understanding a broad human activity (not tied to your product) | General behavior, goals, emotions across a domain | Chronological, free-form, product-agnostic |
| **Empathy Map** | Quick synthesis of what you know about a user type | Says/Does/Thinks/Feels for one persona | Four quadrants + center (goals/needs) |
| **Mental Model Diagram** | Deep understanding of user reasoning and decision-making | Hierarchical breakdown of how users think about a domain | Bottom-up laddering, towers grouped into spaces |
| **Ecosystem Model** | Visualizing relationships between actors, systems, and content | Flows of value between entities | Network/spatial layout, concentric rings |
| **User Story Map** | Planning product features against user workflow | Activities → Steps → Details for backlog prioritization | Grid: activities across top, priority top-to-bottom |

### Quick Selection Guide

- **"We need to understand our customer's experience"** → Customer Journey Map
- **"Our departments aren't coordinated"** → Service Blueprint
- **"We need to understand the problem space before designing"** → Experience Map
- **"We need a quick picture of our user"** → Empathy Map
- **"We need to understand how users think about this domain"** → Mental Model Diagram
- **"We need to see how all the pieces connect"** → Ecosystem Model
- **"We need to prioritize our backlog"** → User Story Map

For detailed guidance on each type, see `references/customer-journey-maps.md`, `references/service-blueprints.md`, and `references/experience-maps-and-models.md`.

---

## The Mapping Process

Every alignment diagram follows four phases:

### Phase 1: Initiate

Frame the effort before you start drawing.

1. **Define the experience to map** — Which persona? Which scenario? What scope (end-to-end journey or a specific flow)?
2. **Select the diagram type** — Use the selection guide above
3. **Identify stakeholders** — Who needs to be in the room? Product trio minimum; include frontline staff when possible
4. **Assess formality level** — Quick whiteboard session or formal multi-week effort?
5. **Write a brief** — One page: goals, persona, scenario, scope, timeline, participants

### Phase 2: Investigate

Map with evidence, not assumptions. A diagram based on assumptions is an assumption.

1. **Audit existing sources** — Analytics, support tickets, surveys, prior research, NPS comments, call center logs
2. **Create a touchpoint inventory** — List every physical, digital, and person-to-person interaction point. Note channel and collect screenshots/photos
3. **Draft an assumption map** — Have the team sketch the journey from memory. Mark what you're confident about vs. what's a guess. This reveals what research needs to fill in
4. **Conduct research** — Interviews (story-based), contextual inquiry, diary studies, service safaris. See `ux-research` skill for method guidance
5. **Analyze and synthesize** — Affinity diagramming, thematic coding. Extract observations into atomic notes coded to source participants

**Minimum viable investigation:** 5 user interviews + analytics review + touchpoint inventory. This is enough to create a credible first-version map.

### Phase 3: Illustrate

Assemble insights into a single, readable diagram.

**Content syntax rules** (keep these consistent throughout any diagram):

| Element | Syntax Rule | Example |
|---|---|---|
| **Actions** | Start with a verb | "Downloads app," "Calls support" |
| **Thoughts** | Phrase as a question | "Are there hidden fees?" "Who else do I need to involve?" |
| **Feelings** | Use adjectives | "Nervous," "Relieved," "Frustrated" |
| **Pain points** | Start with a gerund | "Waiting for installation," "Re-entering information" |
| **Touchpoints** | Use nouns (the interface) | "Email," "Mobile app," "Customer hotline" |
| **Opportunities** | Start with a change verb | "Eliminate unnecessary steps," "Automate follow-up email" |

**Layout principles:**
- Time flows left to right
- More important information is visually larger/higher
- Use a consistent color system: one color for pain points (red), one for opportunities (green), one for neutral information
- Every row/lane should have a clear label
- The emotional curve (if included) should be immediately scannable

**Iteration process:**
1. Start in a spreadsheet or whiteboard — get the content right first
2. Move to a structured layout (Miro, FigJam, or drawing tool)
3. Refine visual hierarchy — not everything is equally important
4. Get feedback from stakeholders before polishing
5. Polish only after content is validated

### Phase 4: Align

The diagram is a means to an end. Use it.

1. **Alignment workshop** — Walk through the diagram with the team. See `references/alignment-workshops.md`
2. **Identify moments of truth** — Critical, emotionally intense moments that make or break the relationship
3. **Find opportunities** — Look at weaknesses, gaps, redundancies, and where competitors perform well
4. **Prioritize** — Score opportunities by user impact × feasibility
5. **Envision** — Generate solutions with scenarios, storyboards, wireframes
6. **Plan** — Connect opportunities to the product roadmap or backlog

---

## Customer Journey Map: Core Structure

A CJM tells the story of one persona going through one scenario.

### Required Elements

| Row | Content |
|---|---|
| **Phases** | 3-7 high-level stages (e.g., Awareness → Research → Purchase → Onboarding → Use → Renewal) |
| **Goals** | What the user is trying to accomplish at each phase |
| **Actions** | What the user does (verb-first) |
| **Touchpoints** | Which channels/interfaces are involved |
| **Thinking** | Questions or thoughts at each phase |
| **Feeling** | Emotional state — use a sentiment curve (positive ↔ negative) |
| **Pain points** | Barriers, frustrations, friction |
| **Opportunities** | How to improve each phase |

### Optional Elements

- **Ownership** — Which team owns each phase
- **Moments of truth** — Flag the 2-3 moments that define the relationship
- **Metrics** — KPIs or data points at each phase (conversion rate, NPS, support tickets)
- **Channels** — Detailed breakdown of touchpoints by channel

For the full reference with examples and a step-by-step process, see `references/customer-journey-maps.md`.
For a fillable template, see `templates/customer-journey-map-template.md`.

---

## Service Blueprint: Core Structure

A service blueprint extends the journey map by showing how the organization delivers the experience.

### Five Swimlanes

1. **Physical Evidence** — Tangible artifacts the customer interacts with (screens, receipts, signage)
2. **Customer Actions** — What the customer does at each step
3. **Frontstage (Onstage)** — Employee/system actions visible to the customer
4. **Backstage** — Internal actions not visible to the customer but directly supporting the experience
5. **Support Processes** — Infrastructure, systems, and third-party services that enable everything

### Three Critical Lines

- **Line of Interaction** — Separates customer from frontstage (the interface)
- **Line of Visibility** — Separates frontstage from backstage (what the customer can vs. cannot see)
- **Line of Internal Interaction** — Separates backstage from support processes

### When to Use a Blueprint vs. a Journey Map

| Signal | Use Blueprint |
|---|---|
| Departments aren't coordinated | Yes |
| Need to redesign internal processes | Yes |
| Launching a new service | Yes |
| Optimizing operations | Yes |
| Understanding customer emotions | Journey map is sufficient |
| Exploring a problem space | Experience map is better |

For the full reference, see `references/service-blueprints.md`.
For a fillable template, see `templates/service-blueprint-template.md`.

---

## Empathy Map: Core Structure

A fast synthesis tool — use when you need a quick picture of a user segment.

### Four Quadrants + Center

| Quadrant | Content | Source |
|---|---|---|
| **Says** | Direct quotes, verbatim statements | Interviews, surveys |
| **Does** | Observable actions and behaviors | Observation, analytics |
| **Thinks** | Beliefs, concerns, internal monologue (may not be spoken) | Inference from behavior + interviews |
| **Feels** | Emotional states, worries, hopes | Tone, body language, explicit statements |
| **Center: Goals & Needs** | What this user is trying to achieve and what they need to succeed | Synthesis of all four quadrants |

**Rules:**
- One empathy map per persona or user segment
- Base it on research, not assumptions. If you haven't talked to users, label it "Proto-Empathy Map"
- Thinks ≠ Says. The gap between them is where insight lives
- 5-10 items per quadrant is a good target

For a fillable template, see `templates/empathy-map-template.md`.

---

## Moments of Truth

Moments of truth are critical, emotionally intense moments that define the relationship between a person and a service. They are the moments when expectations are confirmed or shattered.

### How to Identify Them

1. Look for **high emotional intensity** — peaks and valleys on the sentiment curve
2. Look for **irreversible decisions** — signup, purchase, cancellation
3. Look for **first impressions** — first use, first contact with support
4. Look for **failure/recovery moments** — what happens when things go wrong
5. Ask users: "Tell me about a time when you almost gave up" or "What moment stands out?"

### Types of Moments of Truth

| Moment | Definition | Example |
|---|---|---|
| **Zero Moment** (ZMOT) | When the person first discovers or searches for the service | Reading a review, hearing from a friend |
| **First Moment** | First direct interaction with the product/service | Landing page, store visit, first login |
| **Second Moment** | Actual experience of using the product/service | Core workflow, daily use |
| **Ultimate Moment** | When the person becomes an advocate (or detractor) | Recommending to others, writing a review |

### Design Implications

- **Peak-End Rule** — People remember the peak emotional moment and the ending. Design both deliberately
- **Recovery moments** are often more powerful than smooth moments. A well-handled failure builds more loyalty than seamless success
- **Flag moments of truth on every diagram** — They should be the most visually prominent elements

---

## Common Mistakes

| Mistake | Why It Fails | Instead |
|---|---|---|
| Mapping from assumptions, not research | Confirms biases, misses real pain points | Interview 5+ users before mapping |
| Too many phases (10+) | Unreadable, loses the story | 3-7 phases. Merge or split as needed |
| Mapping the ideal journey, not the real one | Produces a marketing brochure, not a diagnostic tool | Map current state first, then design future state |
| No emotional layer | Misses the most actionable information | Always include a feeling/sentiment row |
| No action after the diagram | Beautiful artifact, zero impact | Schedule an alignment workshop within 2 weeks of finishing |
| Mixing personas in one map | Muddled insights, averaged pain points | One persona per journey map. Compare maps later |
| Skipping the "backstage" | Only sees symptoms, not causes | Even if not a full blueprint, note what's behind each touchpoint |
| Making it too polished too early | Discourages input and iteration | Start rough. Polish after validation |

---

## Quick Reference: Content Checklist

Before finalizing any alignment diagram, verify:

- [ ] **Based on research** — Can you trace every element to a source (participant, data point, observation)?
- [ ] **One persona, one scenario** — Is the scope clear and focused?
- [ ] **Consistent syntax** — Actions start with verbs, thoughts are questions, feelings are adjectives?
- [ ] **Emotional layer included** — Can you see the sentiment curve or feeling states?
- [ ] **Moments of truth flagged** — Are the 2-3 critical moments visually prominent?
- [ ] **Opportunities identified** — Does the diagram point toward what to do next?
- [ ] **Ownership assigned** — Does each phase/touchpoint have a team or person responsible?
- [ ] **Workshop scheduled** — Is there a plan to use this diagram, not just admire it?

---

## Reference Files

- `references/customer-journey-maps.md` — Full CJM process, elements, variations, and tips
- `references/service-blueprints.md` — Blueprint construction, swimlanes, lines, and organizational use
- `references/experience-maps-and-models.md` — Experience maps, mental model diagrams, ecosystem models
- `references/alignment-workshops.md` — Workshop facilitation, exercises, and follow-through

## Templates

- `templates/customer-journey-map-template.md` — Fillable CJM with all standard rows
- `templates/service-blueprint-template.md` — Fillable blueprint with five swimlanes
- `templates/empathy-map-template.md` — Fillable four-quadrant empathy map

## Examples

- `examples/cjm-walkthrough.md` — End-to-end example: from research to finished journey map
- `examples/diagram-selection-scenarios.md` — Real-world scenarios showing which diagram to choose and why
