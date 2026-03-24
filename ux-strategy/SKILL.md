---
name: UX Strategy
description: Connect design decisions to business outcomes through competitive analysis, opportunity mapping, Jobs to Be Done, outcome-driven discovery, value proposition design, and UX metrics. Shape product direction with strategic frameworks grounded in evidence.
---

# UX Strategy

You are an expert in UX strategy — the discipline that connects design decisions to business outcomes and customer value. Your recommendations are grounded in Teresa Torres's Continuous Discovery Habits (Opportunity Solution Trees, outcome-driven discovery), Jim Kalbach's Jobs to Be Done Playbook (job mapping, desired outcomes, switch analysis), Jaime Levy's UX Strategy (competitive analysis, value innovation, funnel design), Jeff Gothelf and Josh Seiden's Lean UX (hypothesis-driven design, outcomes over outputs), and Google's HEART framework for UX metrics.

*UX strategy is the high-level plan to achieve business goals under conditions of uncertainty. It precedes wireframes, visual design, and development. Without it, teams build features no one needs. With it, every design decision traces back to a reason.*

---

## Core Framework

UX strategy sits at the intersection of four concerns:

| Concern | Question | Key Tool |
|---------|----------|----------|
| **Business viability** | Will this sustain the business? | Business Model Canvas, value proposition |
| **Customer desirability** | Do people actually want this? | JTBD interviews, opportunity mapping |
| **Competitive positioning** | Why choose us over alternatives? | Competitive analysis, value innovation |
| **Measurable outcomes** | How do we know it's working? | HEART framework, North Star metric |

All four must be addressed. A desirable product that isn't viable fails. A viable product that isn't desirable is ignored. A product without competitive differentiation gets commoditized. A product without metrics can't improve.

---

## Outcomes Over Outputs

The most common strategic failure: teams measure success by features shipped instead of impact created.

### Types of Outcomes

| Type | Definition | Example | Who Owns It |
|------|-----------|---------|-------------|
| **Business outcome** | Lagging indicator of company health | Revenue, retention rate, market share | Leadership |
| **Product outcome** | Leading indicator a team can directly influence | Activation rate, task completion, engagement frequency | Product trio |
| **Traction metric** | Measures product usage | DAU, sessions/week, feature adoption | Product team |

**The sweet spot is product outcomes.** They're specific enough for a team to influence directly, and they connect upward to business outcomes.

### Setting Outcomes

Outcomes emerge from a two-way negotiation (Torres):
1. Leadership sets strategic context: "We need to improve retention"
2. Product team proposes product outcomes they believe will drive retention: "Reduce time-to-first-value for new users"
3. Both sides agree on the outcome and how to measure it

**When the team is new to an outcome**, set a learning goal ("Discover the key drivers of activation") rather than a performance goal ("Increase activation by 15%"). Learning goals reduce pressure and encourage exploration.

### Anti-patterns

- Pursuing more than 1-2 outcomes at once per team
- Choosing outputs disguised as outcomes ("Launch the redesigned dashboard")
- Setting outcomes without connecting them to business goals
- Picking outcomes in isolation without leadership alignment

---

## Opportunity Mapping

### The Opportunity Solution Tree (OST)

The OST (Torres) is the central strategic artifact. It maps the path from a desired outcome to testable experiments:

```
        [Desired Outcome]
              |
    ┌─────────┼──────────┐
    |         |          |
[Opportunity] [Opportunity] [Opportunity]
    |              |
 ┌──┴──┐      ┌───┴───┐
[Sol A] [Sol B] [Sol C] [Sol D]
   |       |      |
[Test]  [Test]  [Test]
```

**Four layers:**
1. **Outcome** (root) — The business/product outcome the team is pursuing
2. **Opportunities** — Customer needs, pain points, and desires discovered through research
3. **Solutions** — Ideas the team is exploring to address opportunities
4. **Assumption tests** — Experiments to validate which solutions will work

### Writing Good Opportunity Statements

Opportunities must be:
- Written from the **customer's perspective**
- Describing a **need, pain point, or desire** — never a solution
- Grounded in **actual customer stories** — not team assumptions

| Bad (solution in disguise) | Good (opportunity) |
|---------------------------|-------------------|
| "We need a dashboard" | "I can't see how my project is tracking" |
| "Users want notifications" | "I miss important updates because I don't check the app daily" |
| "Add a search filter" | "I waste time scrolling through results that don't match what I need" |

### Structuring the Tree

- **Parent-child**: Broad opportunities break into specific sub-opportunities. "Managing finances is stressful" → "I don't know where my money goes" + "Unexpected bills catch me off guard"
- **Organize by moments in time**: Top-level branches map to distinct moments in the customer journey ("When I first sign up," "When I check my balance," "When I pay a bill")
- **Sibling opportunities should be distinct and comparable** — if two siblings overlap significantly, merge them

### Prioritizing Opportunities

Select a single **leaf-node opportunity** (one without children) to address. Evaluate across:

| Dimension | Question |
|-----------|----------|
| **Opportunity sizing** | How many customers face this? How often? |
| **Market factors** | How does this relate to competitive dynamics? |
| **Company factors** | Does this align with strategy, strengths, resources? |
| **Customer severity** | How painful is this? What workarounds exist? |

Most prioritization decisions are reversible (two-way doors). Don't over-analyze. Pick, explore, and switch if evidence suggests a different path.

---

## Jobs to Be Done (JTBD)

### Core Concept

People don't buy products — they "hire" them to get a job done (Kalbach, Christensen). A job is the process of reaching objectives under given circumstances.

Jobs are:
- **Solution-agnostic** — they exist independent of any product
- **Stable over time** — technology changes, fundamental objectives don't
- **Focused on progress** — people hire solutions to make progress toward goals
- **Contextual** — circumstances matter as much as the objective itself

### Job Structure

| Element | Description | Example |
|---------|------------|---------|
| **Main job** | The overall functional objective | "Prepare a meal for my family" |
| **Related jobs** | Adjacent objectives significantly different from the main job | "Clean up after cooking" |
| **Emotional jobs** | How people want to feel | "Feel confident I'm feeding them well" |
| **Social jobs** | How people want to be perceived | "Be seen as a good host" |

### Job Map (8 Stages)

Jobs unfold as a process (Ulwick):

1. **Define** — Determine objectives and plan
2. **Locate** — Gather materials and information
3. **Prepare** — Organize and set up
4. **Confirm** — Ensure readiness
5. **Execute** — Perform the job
6. **Monitor** — Evaluate success
7. **Modify** — Iterate as necessary
8. **Conclude** — End and follow up

Each stage contains **desired outcomes** — needs formulated as: `[Direction] + [Measure] + [Object] + [Clarifier]`

Example: "Minimize the **time** it takes to **find** relevant job listings **when searching in a new city**"

### Finding Underserved Needs

Plot needs on an importance-satisfaction matrix:

| Quadrant | Importance | Satisfaction | Strategy |
|----------|-----------|-------------|----------|
| **Underserved** | High | Low | Innovate here — highest opportunity |
| **Overserved** | Low | High | Don't invest more — diminishing returns |
| **Table stakes** | High | High | Must maintain — no competitive advantage |
| **Low priority** | Low | Low | Ignore — low impact |

**Opportunity score** (Ulwick): `Importance + (Importance - Satisfaction)`. Scores above 10 signal significant opportunity. Scores above 15 signal extreme opportunity.

### Four Forces of Switching

When customers switch solutions, four forces are at play (Moesta):

| Force | Direction | Example |
|-------|-----------|---------|
| **Push** | Away from current solution | "My current tool crashes during demos" |
| **Pull** | Toward new solution | "That tool has real-time collaboration" |
| **Anxiety** | Resists change | "What if the migration breaks our workflow?" |
| **Habit** | Resists change | "I know all the keyboard shortcuts in the current tool" |

Switching happens when Push + Pull > Anxiety + Habit. Strategy: amplify push and pull while reducing anxiety and habit.

---

## Competitive Analysis

### Types of Competitors (Levy)

| Type | Description | Example |
|------|------------|---------|
| **Direct** | Same value proposition to same customers | Figma vs. Sketch |
| **Indirect (same segment)** | Different value proposition to your customers | Miro vs. Figma (overlapping use cases, different core value) |
| **Indirect (same value)** | Same value proposition to different customers | Canva vs. Figma (design tools, different segments) |
| **JTBD competitors** | Different product entirely, same job | Spreadsheet vs. project management tool (both hired to "track project progress") |

**JTBD competitors are the most dangerous blind spot.** Traditional competitive analysis misses them entirely.

### Competitive Analysis Process

1. **Identify competitors** — 5-8 direct, 3-5 indirect, 2-3 JTBD competitors
2. **Research each** — Product, business model, UX strengths/weaknesses, positioning
3. **Build a comparison matrix** — Attributes as rows, competitors as columns
4. **Analyze** — Find gaps, patterns, table stakes, and opportunities
5. **Write findings brief** — Recommendations with a clear strategic point of view

### Value Innovation (Levy, Kim & Mauborgne)

Value innovation is the simultaneous pursuit of **differentiation and low cost** — creating a leap in value for customers and the business.

**Four patterns:**
1. **New mash-up** — Combine features from different competitors into something new
2. **Innovative slice** — Take one aspect of a broad platform and do it radically better
3. **Consolidation** — Unify disparate experiences into one simple solution
4. **Two-sided connection** — Bring distinct user segments together for unprecedented value

**Market positioning:**
- **Blue ocean** — Uncontested space, no direct competition
- **Red ocean** — Crowded market, fierce competition
- **Purple ocean** — Somewhere in between

Value innovation targets blue ocean. If you're in a red ocean, stop competing on existing attributes and create new ones.

---

## Validating Strategy

### Hypothesis-Driven Design (Gothelf & Seiden)

Replace "requirements" with "assumptions." Everything is a hypothesis until validated.

**Hypothesis format:**
> We believe that [doing this] for [these people] will achieve [this outcome]. We'll know we're right when [measurable signal].

**Validation process:**
1. State assumptions explicitly
2. Identify the riskiest assumption (highest importance × lowest evidence)
3. Design the smallest experiment to test it
4. Define success criteria **before** running the test — use specific numbers ("7 out of 10 participants will..."), not percentages
5. Run the test, evaluate results, iterate

### Assumption Types (Torres)

| Type | Question |
|------|----------|
| **Desirability** | Will customers want this? Will they choose it over alternatives? |
| **Viability** | Does this work for the business? Can we sustain it? |
| **Feasibility** | Can we build this? Do we have the capability? |
| **Usability** | Can customers figure out how to use this? |
| **Ethical** | Could this cause harm? Are there unintended consequences? |

Map assumptions on a 2×2 grid: importance (y-axis) × evidence (x-axis). **Upper-right quadrant** (high importance, low evidence) = "leap of faith" assumptions. Test these first.

### Testing Tools

| Tool | Best For | Speed | Cost |
|------|----------|-------|------|
| **Story-based interviews** | Desirability, understanding current behavior | 1 week | Low |
| **Smoke test / landing page** | Desirability at scale | 1-2 weeks | Low-Medium |
| **Wizard of Oz** | Feasibility of automation (simulate with humans) | 1-2 weeks | Medium |
| **Concierge test** | Desirability of value proposition (deliver manually) | 2-4 weeks | Medium |
| **One-question survey** | Specific assumptions at scale | Days | Low |
| **Data mining** | Behavioral patterns in existing product | Days | Low |
| **Prototype test** | Usability, concept validation | 1-2 weeks | Medium |
| **A/B test** | Solution comparison at scale | 2-4 weeks | Medium-High |

Aim for **10-20 small assumption tests per week** (Torres), not one large study per quarter.

---

## UX Metrics

### HEART Framework (Google)

| Category | Measures | Example Metrics |
|----------|----------|----------------|
| **Happiness** | Satisfaction, perceived ease, NPS | Task satisfaction score, CSAT, SUS |
| **Engagement** | Depth and frequency of use | Sessions/week, features used, time in core workflow |
| **Adoption** | New users, feature uptake | Signups, first-time feature usage, onboarding completion |
| **Retention** | Users who come back | Day-7 retention, monthly active %, churn rate |
| **Task success** | Efficiency and effectiveness | Completion rate, time-on-task, error rate |

**Using HEART:** Pick 1-2 categories most relevant to your current outcome. Don't track all five simultaneously — that's monitoring, not strategy.

### North Star Metric

A single metric that captures the core value your product delivers to customers. It connects product usage to business outcomes.

**Characteristics of a good North Star:**
- Measures **value delivered** (not vanity)
- **Leading indicator** of revenue/retention (not lagging)
- A team can **directly influence** it
- **Simple enough** to rally a team around

| Product Type | North Star Example |
|-------------|-------------------|
| Marketplace | Transactions completed per week |
| SaaS tool | Weekly active teams using core feature |
| Content platform | Quality content consumed per user per week |
| Communication app | Messages sent per user per day |

### Connecting Metrics to Outcomes

```
North Star Metric
    |
    ├── Input Metric 1 (Adoption): New users completing onboarding
    ├── Input Metric 2 (Engagement): Users reaching "aha moment"
    └── Input Metric 3 (Retention): Users active in week 2
         |
         ├── Signal: Users who complete setup within 24 hours
         └── Signal: Users who invite a teammate
```

Measure people, not actions. "500 users completed onboarding" is more meaningful than "1,200 onboarding actions occurred" — one active user can generate many actions.

---

## Strategy Process (End-to-End)

| Phase | Activities | Key Output |
|-------|-----------|------------|
| **1. Frame** | Define business context, set desired outcome, identify constraints | Strategy brief |
| **2. Discover** | Customer interviews, JTBD research, experience mapping | Opportunity map / OST |
| **3. Analyze** | Competitive analysis, market positioning, underserved needs | Competitive findings brief |
| **4. Define** | Value proposition, prioritized opportunities, success metrics | Strategic direction document |
| **5. Validate** | Assumption testing, prototype experiments, smoke tests | Validated/invalidated hypotheses |
| **6. Measure** | Instrument product, track outcomes, close feedback loop | Metrics dashboard, learning log |

This is not linear. Discovery feeds analysis, validation feeds back to discovery, measurement informs the next cycle.

---

## Common Mistakes

| Mistake | Why It Fails | Instead |
|---------|-------------|---------|
| Skipping competitive analysis | Build something the market already has, or miss a critical differentiator | Research 10-15 competitors before ideating |
| Defining strategy as a feature list | Features are outputs. Strategy is about outcomes and positioning | Start with the outcome, then discover opportunities, then ideate solutions |
| Only researching direct competitors | Miss JTBD competitors and substitutes | Include indirect and job-level competitors |
| Setting metrics after launch | No baseline. Can't measure improvement | Define success metrics during strategy phase |
| Treating strategy as a one-time document | Strategy goes stale as market and customers change | Continuous discovery — weekly interviews, quarterly strategy reviews |
| Asking customers what to build | Customers describe problems well but design solutions poorly | Ask about behavior and pain points. Design solutions yourself |
| Optimizing a metric without understanding the job | Metric gaming — improving numbers without improving customer experience | Tie every metric to a job outcome |

---

## Reference Files

Load these for deeper guidance on specific topics:

- `references/outcomes-and-opportunities.md` — Opportunity Solution Trees, outcome types, continuous discovery habits, opportunity prioritization, and the product trio
- `references/competitive-analysis.md` — Competitive research process, analysis matrix, value innovation, market positioning, and competitive findings briefs
- `references/jobs-to-be-done.md` — JTBD framework, job mapping, desired outcomes, switch interviews, four forces, and JTBD-driven personas
- `references/metrics-and-measurement.md` — HEART framework, North Star metrics, funnel metrics, instrumentation, and connecting metrics to outcomes
- `references/value-proposition.md` — Value proposition design, validation process, hypothesis-driven design, MVP strategy, and business model alignment

## Templates

- `templates/strategy-brief-template.md` — Complete UX strategy document for framing a product initiative
- `templates/competitive-analysis-template.md` — Competitive analysis matrix and findings brief
- `templates/competitive-brief-template.md` — Standalone competitive brief for stakeholder communication
- `templates/opportunity-solution-tree-template.md` — OST with guidance for each layer

## Examples

- `examples/strategy-walkthrough.md` — End-to-end UX strategy for a fictional B2B product
- `examples/competitive-analysis-walkthrough.md` — Full competitive analysis of a fictional market
