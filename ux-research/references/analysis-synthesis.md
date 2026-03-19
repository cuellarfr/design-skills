# Analysis & Synthesis

Techniques for turning raw research data into actionable insights, models, and recommendations. Covers affinity diagramming, thematic analysis, persona creation, opportunity mapping, and mental model construction.

## The Goal of Analysis

Turn individual observations into patterns. Turn patterns into insights. Turn insights into recommendations. The output is not a document — it's shared understanding that drives design decisions.

## Affinity Diagramming

The most fundamental synthesis technique. It externalizes observations and lets patterns emerge through spatial grouping.

### Process

**Materials needed:**
- Large room with whiteboard wall space
- Sticky notes (multiple colors help)
- Markers
- Camera to photograph the board

**Steps:**

1. **Extract observations** from notes, recordings, and transcripts
   - Write one observation per sticky note
   - Use the participant's words when possible (direct quotes)
   - Code each note to its source participant (e.g., "P3" in the corner)
   - Types of observations: goals, priorities, tasks, motivators, barriers, habits, relationships, tools, environment

2. **Place all notes on the wall** without organizing

3. **Group silently** — team members move notes into clusters without talking
   - Move notes that seem related together
   - It's okay to move notes others have placed
   - Don't create categories first — let them emerge
   - Aim for 5-15 groups (fewer = too abstract, more = too granular)

4. **Name each cluster** with an insight statement
   - Bad: "Navigation" (too generic, just a label)
   - Good: "Users rely on search because they don't trust the navigation categories"
   - The name should be a finding, not a topic

5. **Identify relationships** between clusters
   - Which clusters reinforce each other?
   - Which are in tension?
   - Are there cause-and-effect relationships?

6. **Prioritize** based on:
   - Frequency: How many participants reflected this theme?
   - Impact: How much does this affect the user's ability to achieve their goal?
   - Business alignment: Does addressing this serve business goals?

7. **Derive recommendations** from each prioritized insight
   - What design action does this insight suggest?
   - What should we do differently?
   - What should we investigate further?

### Analysis Session Format

**Duration:** 2-4 hours depending on data volume

**Agenda:**
1. **Context setting (10 min):** Summarize research goals, participants, methods
2. **Individual review (20 min):** Each team member reviews their notes silently
3. **Note creation (30 min):** Everyone writes observations on sticky notes
4. **Silent grouping (20 min):** Place and cluster notes without talking
5. **Group discussion (30 min):** Walk through clusters, debate groupings, name themes
6. **Insight generation (30 min):** Write insight statements for each cluster
7. **Prioritization (20 min):** Vote on most impactful insights
8. **Action planning (20 min):** Identify recommendations and next steps

## Thematic Analysis

A more structured alternative to affinity diagramming, useful for larger data sets.

### Process

1. **Familiarize** — Read through all data twice
2. **Code** — Tag relevant segments with descriptive codes
3. **Search for themes** — Group codes into broader themes
4. **Review themes** — Check that themes accurately represent the data
5. **Define themes** — Write a clear description of what each theme captures
6. **Report** — Select compelling extracts that illustrate each theme

### Coding Framework

When coding observations, tag them with:
- **Behavior codes:** What users do (actions, workarounds, habits)
- **Attitude codes:** What users think and feel (beliefs, frustrations, desires)
- **Context codes:** Environmental factors (tools, constraints, relationships)
- **Process codes:** Sequences and workflows (steps, triggers, decision points)

## Persona Creation

A persona is a fictional user archetype — a composite model from research data that represents a group of needs and behaviors. Good personas might be the most useful and durable outcome of user research.

### How Many Personas?

As few as possible while representing all relevant behavior patterns. Typically 3-5 for a product.

### Persona Elements

1. **Photo:** A real, relatable photo — not stock photography
2. **Name:** Something that fits the demographic naturally
3. **Demographics:** Realistic without stereotyping
4. **Role:** Closely matching one of your research participants
5. **Quote:** An actual verbatim quote from interviews that embodies a core belief or attitude
6. **Goals:** 3-4 key goals the product will serve or relate to
7. **Behaviors and habits:** Specific, habitual behaviors that define this persona's pattern
8. **Skills:** Level of technical expertise and domain experience
9. **Environment:** Physical, social, and technological context affecting their product use
10. **Relationships:** People who influence their decisions or are affected by them
11. **Frustrations:** Current pain points and barriers
12. **Motivations:** What drives their behavior

### Creating Personas from Research Data

1. Review all interview data and look for behavioral patterns
2. Identify behavioral variables (e.g., frequency of use, tech comfort, decision-making style)
3. Map participants along these variables
4. Identify clusters of similar participants
5. Create one persona per cluster
6. Flesh out with real data from participants in that cluster
7. Validate with the team — do these feel real?

### Scenarios

If personas are your characters, scenarios are your plots. Each scenario tells how a persona interacts with your system to meet their goals.

**Use scenarios to:**
- Flesh out requirements
- Explore potential solutions
- Validate proposed solutions
- Create usability test scripts

**Format:** "When [persona] is [context/trigger], they want to [goal] so they [action sequence]. They feel [emotion] when [outcome]."

## Opportunity Mapping

### Opportunity Solution Tree

A visual framework for mapping the path from business outcomes to customer opportunities to solutions.

**Structure:**
```
Desired Outcome (business metric the team can influence)
├── Opportunity 1 (customer need/pain point/desire)
│   ├── Solution A
│   │   ├── Assumption test 1
│   │   └── Assumption test 2
│   └── Solution B
│       └── Assumption test 3
├── Opportunity 2
│   ├── Solution C
│   └── Solution D
└── Opportunity 3
    └── Solution E
```

**Rules:**
- The desired outcome is a product metric, not a business metric (the team must be able to directly influence it)
- Opportunities come from research — they are customer needs, pain points, and desires
- Break large opportunities into smaller sub-opportunities until they're actionable
- Generate 15-20 solutions per opportunity before evaluating (volume drives quality)
- Choose a target opportunity that is a "leaf node" (no children) before ideating solutions
- Test assumptions, not whole ideas — what must be true for this solution to work?

### Prioritizing Opportunities

Consider:
- **Opportunity size:** How many users are affected?
- **Market factors:** Is this a growing need? Are competitors addressing it?
- **Company factors:** Do we have the capability? Does it align with strategy?
- **Customer factors:** How painful is this? How frequently encountered?

## Mental Model Construction

A mental model diagram represents the user's cognitive space — how they think about a domain, organized into tasks, beliefs, and feelings.

### Process

1. Conduct user research (interviews, contextual inquiry)
2. Create an affinity diagram from the data
3. Place affinity clusters into stacks representing the user's cognitive space
4. Group stacks around the tasks or goals they relate to
5. Map your product's features underneath, aligned to the user's model
6. Gaps between the user's model and your features = opportunities

### Using Mental Models

- "Intuitive" design = design that matches the user's mental model
- Where your product aligns with the mental model → reinforce
- Where your product diverges from the mental model → either adapt the design or plan for learning
- Where the mental model has no coverage → opportunity for new features

## Journey Map Synthesis

### When to Create Journey Maps

After you have:
- Interview data from 5+ participants about the same experience
- A clear understanding of the stages of the experience
- Observations about emotions, pain points, and touchpoints at each stage

### Journey Map Structure

**Header:**
- Customer name/persona
- Scenario description
- Goals and expectations

**For each stage:**

| Element | Description |
|---|---|
| **Goal** | What the user is trying to accomplish |
| **Actions** | What the user does |
| **Touchpoint** | What parts of the product/service are involved |
| **Thinking** | What the user is thinking |
| **Feeling** | Emotional state (use a sentiment curve) |
| **Pain points** | Frustrations and barriers |
| **Opportunities** | How we can improve this stage |
| **Ownership** | Who on the team is responsible |

### Empathy Map

A quicker synthesis tool for articulating what you know about a user type.

**Four quadrants:**
1. **Says** — Direct quotes and statements from research
2. **Does** — Actions and behaviors observed
3. **Thinks** — Thoughts, beliefs, concerns (may not be explicitly stated)
4. **Feels** — Emotional state throughout the experience

**Center:** The user's goals and needs

## Reporting Insights

### Insight Statement Format

A good insight statement has three parts:
1. **Observation:** What we saw (the pattern)
2. **Interpretation:** What it means (the why)
3. **Implication:** What we should do about it (the design direction)

**Example:**
- **Observation:** 4 of 5 participants ignored the sidebar navigation and used search instead
- **Interpretation:** The navigation categories don't match users' mental models for finding content
- **Implication:** We should restructure navigation using terminology from card sort results, and make search more prominent as a primary navigation strategy

### Recommendation Format

Each recommendation should include:
- **Finding:** The insight it addresses
- **Severity:** Critical / High / Moderate / Low
- **Recommendation:** Specific action to take
- **Effort estimate:** Small / Medium / Large
- **Evidence:** Which participants, how many, supporting quotes
