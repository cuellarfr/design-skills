# Customer Journey Maps: Complete Reference

## What a CJM Is (and Isn't)

A Customer Journey Map is a chronological visualization of one persona's experience with a product or service across multiple touchpoints. It tells the story of what users do, think, and feel at each stage.

**A CJM is:**
- A diagnostic tool that reveals pain points, gaps, and opportunities
- A shared reference for cross-functional teams
- A conversation starter, not a conversation ender
- Based on real user research, not stakeholder assumptions

**A CJM is not:**
- A user flow diagram (those show interface steps, not experiences)
- A site map or information architecture
- A process flow (those show business processes, not user experience)
- A marketing funnel (those show conversion, not experience quality)

---

## CJM Elements: The Full Catalog

### Required Elements

Every CJM should include these rows:

#### 1. Phases

High-level stages of the experience. 3-7 phases is the sweet spot.

**Common phase patterns:**

| Context | Typical Phases |
|---|---|
| **Product purchase** | Awareness → Research → Evaluation → Purchase → Onboarding → Use → Renewal/Churn |
| **SaaS onboarding** | Discovery → Signup → Setup → First Use → Habit Formation → Expansion |
| **Service encounter** | Need Recognition → Search → Contact → Service Delivery → Follow-up |
| **Healthcare** | Symptom → Research → Appointment → Visit → Treatment → Recovery |
| **E-commerce** | Browse → Compare → Add to Cart → Checkout → Delivery → Use → Return/Reorder |

**Rules for phases:**
- Name them from the user's perspective, not the business's ("Research" not "Lead Qualification")
- Each phase should represent a distinct user goal
- Phases should be mutually exclusive — a user shouldn't be in two phases simultaneously
- Include pre-product and post-product phases (what happens before they find you and after they stop using you)

#### 2. Goals

What the user is trying to accomplish at each phase.

**Good goals:**
- "Find a solution that fits my budget" (Research phase)
- "Get my team set up without disrupting their work" (Onboarding phase)
- "Understand if this is working for us" (Use phase)

**Bad goals (too vague):**
- "Use the product"
- "Be happy"
- "Get value"

#### 3. Actions

What the user actually does. Start each with a verb.

**Examples:**
- "Searches Google for 'project management tool for small teams'"
- "Compares pricing pages of three competitors in separate tabs"
- "Asks colleague in Slack if they've used this tool before"
- "Watches 2 minutes of the onboarding video, then skips ahead"

**Key:** Include workarounds and unexpected behaviors, not just the happy path. If users copy data into a spreadsheet because the export doesn't work, that's an action.

#### 4. Touchpoints

Which channels or interfaces the user interacts with at each phase.

**Touchpoint categories:**
- **Digital:** Website, mobile app, email, push notification, chatbot, social media
- **Human:** Sales call, support chat, in-person meeting, phone call
- **Physical:** Store, packaging, printed materials, hardware device
- **Environmental:** Office context, commute, home setting

#### 5. Thinking

What's going through the user's mind. Phrase as questions — this reveals information gaps.

**Examples:**
- "Is this worth the price, or is there a free alternative?"
- "Will my team actually adopt this?"
- "Why can't I find the setting I'm looking for?"
- "Do I need to talk to IT before I can proceed?"

#### 6. Feeling / Sentiment Curve

The emotional state at each phase. This is the most diagnostic layer — pain points live in emotional valleys.

**Three ways to represent emotion:**

1. **Sentiment curve** — A line graph running across all phases, moving above (positive) and below (negative) a neutral midline. Most common and most scannable.

2. **Emotion labels** — Adjectives at each phase: "Excited," "Confused," "Frustrated," "Relieved," "Satisfied." Use a limited palette (5-7 adjectives) for consistency.

3. **Emoji scale** — Quick shorthand for workshops: 😡 😟 😐 🙂 😄

**The gap between Thinking and Feeling is insight.** If a user is thinking "This seems straightforward" but feeling anxious, there's a hidden barrier.

#### 7. Pain Points

Barriers, frustrations, and friction at each phase. Start each with a gerund.

**Examples:**
- "Re-entering information already provided during signup"
- "Waiting 24 hours for a response from support"
- "Navigating a settings menu with 30+ options"
- "Having to switch between mobile and desktop to complete the task"

**Severity indicators:** Mark pain points as Critical / High / Moderate / Low using the same scale as usability findings (see ux-research skill).

#### 8. Opportunities

How to improve each phase. Start each with a change verb.

**Examples:**
- "Pre-fill form fields from signup data"
- "Add live chat during business hours for the first 7 days"
- "Reduce settings to 10 most-used options; move rest to 'Advanced'"
- "Enable full workflow completion on mobile"

---

### Optional Elements

Add these when they strengthen the story:

| Element | When to Include | Format |
|---|---|---|
| **Ownership** | When multiple teams own different phases | Team/person name per phase |
| **Moments of truth** | Always recommended | Flag icon or highlighted row |
| **Metrics/KPIs** | When connecting to analytics | Data points per phase (conversion %, NPS, tickets) |
| **Channels** | When omnichannel experience matters | Channel breakdown per touchpoint |
| **Backstage glimpse** | When internal processes affect experience | Brief note on what's happening behind the scenes |
| **Competitor comparison** | When benchmarking | Side-by-side or overlay |
| **Time** | When duration matters | Approximate time spent per phase |

---

## Building a CJM: Step-by-Step Process

### Step 1: Define Scope

Answer these questions before starting:

- **Who?** — Which persona? (One per map)
- **What scenario?** — What is the persona trying to accomplish?
- **Where does it start?** — What triggers the journey? (A need, a problem, a recommendation?)
- **Where does it end?** — What's the final state? (Purchase? Renewal? Churn?)
- **Current state or future state?** — Always map current state first

Write a one-sentence scope statement: "*[Persona] trying to [goal] from [starting trigger] to [end state]*."

**Example:** "Sarah, a marketing manager, trying to set up a project management tool for her team, from first hearing about it from her boss to completing her first project."

### Step 2: Gather Data

Minimum viable data set:
- **5+ user interviews** — Story-based, focused on the journey you're mapping
- **Analytics** — Funnel data, feature usage, time-on-task, drop-off points
- **Support data** — Top tickets, common complaints, FAQ patterns
- **Touchpoint inventory** — Screenshots/photos of every interaction point

**Interview questions for journey mapping:**

- "Walk me through what happened from the very beginning. What first made you aware of [product/need]?"
- "What did you do next? And then what?"
- "At that point, what were you thinking?"
- "How did that make you feel?"
- "Was there a moment when you almost gave up? Tell me about that."
- "What was the best part of the experience? The worst?"
- "If you could change one thing about the whole process, what would it be?"

### Step 3: Create an Assumption Map

Before analyzing research, have the team sketch the journey from memory.

1. Get the product trio (PM, designer, engineer) in a room
2. Give them sticky notes and a whiteboard with phase columns
3. Ask them to fill in: What do users do? Think? Feel? Where do they struggle?
4. Compare the assumption map to the research data
5. Circle areas where assumptions were wrong — these are the most valuable insights

### Step 4: Synthesize Research into the Map

For each phase:
1. Code interview transcripts by phase
2. Extract actions (what they did), thoughts (what they said/wondered), feelings (emotional state)
3. Identify pain points where multiple participants struggled
4. Note touchpoints involved
5. Write opportunities based on the pain points

**Frequency matters:** Mark how many participants experienced each pain point. A pain point mentioned by 4 of 5 users is more actionable than one mentioned by 1.

### Step 5: Draft the Layout

**Recommended structure (for markdown or whiteboard):**

```
| Phase →        | Phase 1    | Phase 2    | Phase 3    | Phase 4    |
|----------------|------------|------------|------------|------------|
| Goal           |            |            |            |            |
| Actions        |            |            |            |            |
| Touchpoints    |            |            |            |            |
| Thinking       |            |            |            |            |
| Feeling        | 😄/😐/😟  | 😄/😐/😟  | 😄/😐/😟  | 😄/😐/😟  |
| Pain Points    |            |            |            |            |
| Opportunities  |            |            |            |            |
| Ownership      |            |            |            |            |
```

### Step 6: Validate and Iterate

1. Walk through the map with 2-3 users: "Does this match your experience?"
2. Present to the team and stakeholders
3. Mark disagreements or unknowns
4. Update based on feedback
5. Only then move to a polished visual format

---

## CJM Variations

### Current State vs. Future State

| Aspect | Current State | Future State |
|---|---|---|
| **Based on** | Research data | Design vision + validated assumptions |
| **Purpose** | Diagnose problems | Communicate intended experience |
| **When** | Before design | After ideation, before build |
| **Validation** | Against user research | Against prototypes and experiments |

**Process:** Current state map → Identify top pain points → Ideate solutions → Draft future state map → Prototype and test → Iterate

### Macro vs. Micro Journey Maps

- **Macro map** — End-to-end journey across weeks/months. Good for strategic planning
- **Micro map** — Detailed view of one phase or one critical flow. Good for tactical design decisions

**Rule of thumb:** Start macro, then create micro maps for phases with the most pain points.

### Comparative Journey Maps

Side-by-side maps for:
- **Two personas** — How does the journey differ for a novice vs. expert?
- **Two channels** — How does the journey differ on mobile vs. desktop?
- **Your product vs. competitor** — Where do you win and where do you lose?

---

## Making CJMs Actionable

A CJM that doesn't lead to action is decorative. Here's how to make it work:

### Connect to Prioritization

For each pain point, assess:

| Criterion | Scale |
|---|---|
| **User impact** | How much does this pain point affect the user's ability to achieve their goal? (1-5) |
| **Frequency** | How many users experience this? (1-5) |
| **Business impact** | Does this pain point cause churn, reduce revenue, or increase support costs? (1-5) |
| **Effort to fix** | How hard is the solution? (1-5, where 1 = easy) |

**Priority score** = (User Impact + Frequency + Business Impact) / Effort

### Connect to the Backlog

Map each opportunity to:
- An existing backlog item (link them)
- A new story/ticket (create it)
- A future research question (if more investigation is needed)

### Keep It Alive

- **Review quarterly** — Is the map still accurate?
- **Update after major releases** — Did the pain points change?
- **Display visibly** — Print it, post it on the wall, link it in the project wiki
- **Reference in design reviews** — "This feature addresses Pain Point 3 in the Onboarding phase"
