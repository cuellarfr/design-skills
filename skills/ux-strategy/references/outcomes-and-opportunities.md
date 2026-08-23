# Outcomes and Opportunities

How to set meaningful outcomes, map the opportunity space, and run continuous discovery. Grounded in Teresa Torres's Continuous Discovery Habits and Jeff Gothelf & Josh Seiden's Lean UX.

---

## The Product Trio

The ideal discovery unit is the **product trio** (Torres): a product manager, a designer, and a software engineer making decisions collaboratively.

| Role | Brings | Evaluates |
|------|--------|-----------|
| **Product manager** | Business context, stakeholder alignment | Viability — will this sustain the business? |
| **Designer** | User understanding, experience craft | Desirability and usability — do people want and can they use this? |
| **Engineer** | Technical knowledge, feasibility awareness | Feasibility — can we build this? At what cost? |

The trio should make product decisions together, not in sequential handoffs. All three participate in interviews, ideation, and assumption testing.

---

## Setting Outcomes

### The Negotiation

Outcomes should emerge from a two-way conversation between leadership and the product team:

1. **Leadership provides strategic context**: "Our Q3 priority is improving retention for enterprise accounts"
2. **Team proposes product outcomes**: "We believe reducing time-to-first-value for enterprise onboarding will improve retention"
3. **Negotiate and commit**: Both sides agree on the specific outcome and how to measure it

### Outcome Quality Checklist

A good product outcome:
- [ ] Is a **leading indicator** of a business outcome (not lagging)
- [ ] Can be **directly influenced** by the product team's work
- [ ] Is **measurable** with data the team can access
- [ ] Is **scoped** enough for one team to own
- [ ] Connects clearly to a **business outcome** leadership cares about
- [ ] Is stated as a **change in behavior**, not a feature ("Users complete onboarding within 24 hours" not "Build onboarding wizard")

### Learning Goals vs. Performance Goals

| Situation | Goal Type | Example |
|-----------|-----------|---------|
| Team knows the space well, has baseline data | **Performance goal** | "Increase 7-day retention from 40% to 55%" |
| Team is new to the outcome or space | **Learning goal** | "Discover the top 3 barriers to enterprise onboarding" |
| Outcome is ambiguous or multi-causal | **Learning goal first**, then performance goal | "Identify which onboarding steps correlate with retention, then set target" |

Learning goals are not weaker than performance goals. They're the appropriate first step when a team lacks sufficient understanding to set meaningful targets.

---

## The Opportunity Solution Tree (OST)

### Building the Tree

**Layer 1 — Outcome (root):**
State the desired product outcome at the top. One tree per outcome. If the team has two outcomes, build two trees.

**Layer 2 — Opportunities:**
Customer needs, pain points, and desires discovered through weekly interviews. Structure as a hierarchy:

- **Top-level branches**: Distinct moments in the customer journey
- **Child opportunities**: Specific needs within each moment
- **Leaf nodes**: Specific enough to address directly

Example:
```
Outcome: Reduce time-to-first-value for enterprise users
├── When I first sign up
│   ├── I don't know where to start
│   ├── The setup requires information I don't have readily available
│   └── I can't tell if the setup is working correctly
├── When I try to use a core feature for the first time
│   ├── I can't find the feature I was promised in the sales demo
│   ├── The feature works differently than I expected
│   └── I need to configure settings before I can do anything useful
└── When I try to get my team to adopt
    ├── I can't explain the value to my team without a lot of effort
    ├── Each team member has to repeat the same setup process
    └── There's no way to share what I've already configured
```

**Layer 3 — Solutions:**
For the prioritized leaf-node opportunity, generate 15-20 ideas individually (Torres), then share as a trio. Select **3 diverse solutions** for further exploration — not 1 (too narrow), not 10 (too scattered).

**Layer 4 — Assumption tests:**
For each solution, identify assumptions across all five types (desirability, viability, feasibility, usability, ethical). Map them on importance × evidence. Test "leap of faith" assumptions first.

### Maintaining the Tree

The OST is a **living artifact**, not a one-time deliverable:
- Update after every customer interview
- Add new opportunities as they emerge
- Archive opportunities that turn out to be less important than expected
- Move between branches as evidence accumulates

### Anti-patterns

| Anti-pattern | Signal | Fix |
|-------------|--------|-----|
| **Solutions in the opportunity layer** | "I need a dashboard" | Reframe: "I can't see how my project is tracking" |
| **Feelings as opportunities** | "I feel frustrated" | Ask: What specifically causes the frustration? |
| **Vertical tree** (no branching) | One parent → one child → one grandchild | Explore more breadth in interviews |
| **Flat tree** (everything at one level) | 15 opportunities with no hierarchy | Group by moments in time or themes |
| **Tree not updated in 2+ weeks** | Same tree from last month | Schedule weekly tree maintenance after synthesis |

---

## Continuous Interviewing

### Why Weekly

Traditional research is project-based — commission a study, wait weeks, get a report. By the time insights arrive, context has changed. Weekly interviewing makes customer understanding a habit, not an event.

**Minimum cadence:** One customer interview per week, conducted by the product trio (not delegated to a separate research team).

### Story-Based Interviewing

The core technique: ask customers to share **specific stories about past behavior**, not opinions, preferences, or hypothetical futures.

Why stories work:
- People confabulate reasons for their behavior (the "left brain interpreter" phenomenon). Asking "Why did you...?" triggers rationalization, not truth
- Stories about specific instances reveal actual behavior, workarounds, and pain points
- Stories provide context that abstract questions miss

**Key practices:**

| Practice | How |
|----------|-----|
| **Separate research questions from interview questions** | Research questions guide your agenda but are never asked directly. Design interview questions that elicit stories revealing answers |
| **Excavate stories** | "Tell me about the last time you..." → "What happened next?" → "What was that like?" |
| **Stay in the past** | "Tell me about a time when..." not "What would you do if..." |
| **Follow the energy** | When the participant's voice changes (frustration, excitement), dig deeper |

### Interview Snapshots

After each interview, create a one-page summary:

```
Participant: [Name/ID]
Date: [Date]
Context: [Role, how they use the product, relevant circumstances]

Key stories:
1. [Story summary — what happened, what they did, how it went]
2. [Story summary]

Opportunities identified:
- [Need/pain point/desire, in customer's language]
- [Need/pain point/desire]

Notable quotes:
- "[Direct quote]"
- "[Direct quote]"

Surprises:
- [Anything that challenged the team's assumptions]
```

### Automated Recruiting

Set up a continuous pipeline rather than scrambling before each session:

| Method | How | Best For |
|--------|-----|----------|
| **In-product intercept** | Trigger a scheduling tool after key actions | Active users |
| **Customer success referrals** | CS team flags interesting conversations | Engaged customers |
| **Customer panel** | Regular draws from an opt-in pool | Broad coverage |
| **Post-support survey** | "Would you chat with our product team?" | Users with recent pain points |

---

## Ideation

### Generate Alone, Share Together

Group brainstorming has well-documented problems (Torres): social loafing, group conformity, production blocking, downward norm setting. The fix:

1. Each trio member generates ideas **individually** — aim for 15-20 each
2. Share all ideas with the group
3. Build on each other's ideas to create new combinations
4. **Dot-vote** to select roughly 3 diverse solutions for further exploration

### Getting Unstuck

When ideas dry up:
- **Incubation** — Take a break. Let the subconscious work
- **Analogous products** — How do other industries solve similar problems?
- **Extreme users** — What would a power user need? A complete novice?
- **Wild ideas** — Deliberately suggest impractical ideas to break mental constraints
- **Reverse the problem** — "How would we make this problem worse?" Then invert

### Why Three Solutions

Exploring three solutions (not one, not ten) forces **compare and contrast**, which produces better evaluation than a "whether or not" decision about a single idea. Three is enough for diversity while remaining manageable for assumption testing.

---

## Co-Evolution of Problem and Solution

An important insight from Torres: the problem space and solution space **evolve together**. Learning about opportunities suggests solutions. Exploring solutions reveals new opportunities.

This means:
- Don't finish mapping all opportunities before ideating solutions
- Don't finalize solutions before exploring more opportunities
- The tree grows in all directions simultaneously
- This is expected behavior, not a process failure

---

## Showing Your Work

### Why It Matters

Product trios don't operate in isolation. They need buy-in from leadership, sales, marketing, engineering managers. Making discovery visible builds trust and prevents stakeholder surprises.

### How to Show the OST

1. **Walk through the reasoning** — Don't present conclusions. Show the outcome, opportunities discovered, solutions explored, and evidence gathered
2. **When stakeholders disagree** — Don't argue about who's right. Frame the disagreement as different assumptions and design tests to resolve them
3. **Slow down** — The trio has weeks of context that stakeholders lack. Take time to build shared understanding

### Anti-patterns in Stakeholder Communication

| Anti-pattern | Problem | Fix |
|-------------|---------|-----|
| Telling, not showing | Stakeholders can't evaluate reasoning they can't see | Walk through the tree, not just the conclusion |
| Curse of knowledge | Assuming stakeholders have the trio's context | Start from the outcome, build up layer by layer |
| Overwhelming with details | 47 interview findings in one meeting | Focus on 3-5 key insights that drive the recommendation |
| Arguing about ideas | Opinion-based debates with no resolution | Design an experiment to resolve the disagreement |
