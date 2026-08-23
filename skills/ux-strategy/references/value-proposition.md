# Value Proposition Design

How to define, validate, and communicate the strategic promise your product makes to customers. Grounded in Jaime Levy's UX Strategy, Alexander Osterwalder's Value Proposition Canvas, Jeff Gothelf's Lean UX, and JTBD principles.

---

## What Is a Value Proposition?

A value proposition is the promise of value your product delivers to a specific customer segment. It answers: **Why should someone choose this over every alternative — including doing nothing?**

A strong value proposition has three properties:
1. **Specific** — Names the customer segment and their core need
2. **Differentiated** — States why this is better than alternatives
3. **Credible** — Can be substantiated with evidence

### Value Proposition Statement

**Template (Levy):**
> It's [type of product] for [customer segment] that [key differentiator].

**Template (Geoffrey Moore):**
> For [target customer] who [key need/job], [product name] is a [category] that [key benefit]. Unlike [primary alternative], we [primary differentiation].

**Examples:**

| Product | Statement |
|---------|-----------|
| Figma | For product teams who need to design collaboratively, Figma is a design tool that runs in the browser with real-time multiplayer. Unlike Sketch, we eliminate file versioning and enable live collaboration |
| Linear | For software teams who need to track work, Linear is a project management tool that's opinionated about speed and keyboard-first interaction. Unlike Jira, we prioritize velocity and developer experience over configurability |

### Value Proposition Quality Check

- [ ] Can you state it in one sentence?
- [ ] Does it name a specific customer segment (not "everyone")?
- [ ] Does it reference a real need (validated through research, not assumed)?
- [ ] Does it state a clear differentiator from the primary alternative?
- [ ] Would a customer recognize the need as their own?
- [ ] Is the differentiator something you can actually deliver?

---

## The Value Proposition Canvas (Osterwalder)

A visual tool for aligning your offering with customer needs.

### Customer Profile (Right Side)

| Element | Description | Source |
|---------|------------|--------|
| **Jobs** | What the customer is trying to get done (functional, emotional, social) | JTBD interviews, job mapping |
| **Pains** | Negative aspects of getting the job done — frustrations, risks, obstacles | Customer interviews, support data, reviews |
| **Gains** | Positive outcomes the customer desires — benefits, expectations, surprises | Desired outcome statements, switch interviews |

### Solution Profile (Left Side)

| Element | Description | Alignment |
|---------|------------|-----------|
| **Products & Services** | Your offering and its features | Must map to jobs |
| **Pain Relievers** | How your offering addresses customer pains | Each reliever should map to a specific pain |
| **Gain Creators** | How your offering creates customer gains | Each creator should map to a specific gain |

### Fit

Value proposition fit occurs when:
- Pain relievers address the **most important** pains (not all pains — the critical ones)
- Gain creators deliver the **most desired** gains
- Products & services get the **main job** done

**Lack of fit signals:**
- Pain relievers address pains customers don't have
- Gain creators deliver gains customers don't value
- The product does something well that nobody asked for
- Customer interviews reveal needs your offering doesn't address

---

## Validating the Value Proposition

### The Validation Hierarchy

Validate in order of risk and cost:

| Level | Method | What It Validates | Cost | Confidence |
|-------|--------|------------------|------|------------|
| **1. Problem interviews** | Conversation with target customers | The problem/job exists and is painful | Low | Directional |
| **2. Solution interviews** | Show concept, observe reaction | The proposed solution addresses the problem | Low | Directional |
| **3. Smoke test** | Landing page, signup form, fake door | Demand exists — people will take action | Low-Medium | Moderate |
| **4. Concierge test** | Deliver value manually to real customers | The value proposition works in practice | Medium | High |
| **5. Wizard of Oz** | Automate the front, human-power the back | The experience works before building the tech | Medium | High |
| **6. MVP** | Minimal functional product | Customers will use (and pay for) the actual product | Medium-High | High |
| **7. A/B test** | Compare variants with real users | Which version delivers more value | Medium-High | Highest |

Don't skip levels. A landing page test costs days; a failed MVP costs months.

### Problem Interviews (Levy)

Validate that the problem exists and matters before designing anything.

**Structure:**
1. **Screening questions** (5 min) — Qualify that this person is your target segment
2. **Current behavior** (10 min) — "How do you currently [get this job done]?" "What's the hardest part?"
3. **Pain exploration** (10 min) — "Tell me about the last time [pain point] happened. What did you do?"
4. **Solution pitch** (5 min) — Describe your proposed value proposition. "Would this help? How?"
5. **Commitment test** (2 min) — "Would you sign up for early access?" "Would you pay for this?"

**Key rules:**
- Ask about past behavior, not hypothetical futures
- Listen for workarounds — they signal genuine pain
- The "money-shot question" (Levy): pitch your hypothetical solution and watch the reaction. Enthusiasm = signal. Politeness = noise

### Lean Validation Loop (Gothelf & Seiden)

```
Hypothesis → Experiment → Evidence → Iterate
    ↑                                    |
    └────────────────────────────────────┘
```

**Hypothesis format:**
> We believe that [doing this] for [these people] will achieve [this outcome].
> We'll know we're right when [specific, measurable signal].

**Rules:**
- Define success criteria **before** running the experiment
- Use specific numbers: "7 out of 10 participants will sign up" — not "70%"
- Time-box experiments: 1-2 weeks maximum for early validation
- One hypothesis per experiment. Don't test multiple things at once

---

## Proto-Personas (Gothelf & Seiden)

When you can't do full JTBD research yet, create proto-personas to align the team on assumptions.

**Four components:**
1. **Name and snapshot** — A name and rough sketch (humanizes the discussion)
2. **Behavioral demographics** — Not age/gender but: tech savviness, frequency of need, budget, decision authority
3. **Behaviors** — How they currently get the job done, what tools they use, what workarounds they employ
4. **Needs and goals** — What they're trying to achieve (stated as jobs, not features)

**Important:** Proto-personas are **assumptions**, not research. Label them as such. Validate and update through actual customer interviews.

---

## Business Model Alignment

### Business Model Canvas (Osterwalder)

The value proposition sits within a broader business model. UX strategy must account for all nine building blocks:

| Block | Question | UX Impact |
|-------|----------|-----------|
| **Customer Segments** | Who are we serving? | Defines who we design for. Different segments may need different experiences |
| **Value Propositions** | What value do we deliver? | The core of UX strategy |
| **Channels** | How do customers find and use us? | Informs touchpoint design and distribution strategy |
| **Customer Relationships** | What relationship do customers expect? | Self-serve vs. high-touch affects the entire UX |
| **Revenue Streams** | How do we make money? | Pricing model affects feature access, upgrade flows, monetization UX |
| **Key Resources** | What do we need to deliver? | Constrains what's feasible to build |
| **Key Activities** | What must we do well? | Prioritizes which UX problems matter most |
| **Key Partnerships** | Who do we need to work with? | Integration points, data dependencies, co-branded experiences |
| **Cost Structure** | What are our costs? | Constrains solution complexity and support model |

### Revenue Model Impact on UX

| Model | UX Implication |
|-------|---------------|
| **Freemium** | Free tier must deliver enough value to hook users. Upgrade path must feel natural, not punitive. Feature gating needs careful design |
| **Subscription** | Onboarding is critical (time-to-value determines conversion). Retention is existential. Cancellation flow is strategic |
| **Marketplace** | Both sides must find value. Trust and safety UX is critical. Supply-demand balance affects the experience |
| **Transaction** | Checkout flow is the bottleneck. Cart abandonment is the key metric. Trust signals (reviews, guarantees) matter enormously |
| **Advertising** | User attention is the product. Ad experience quality affects retention. Balance monetization with user experience |

---

## MVP Strategy (Gothelf & Seiden)

### Types of MVPs

| Type | Fidelity | What It Tests | When to Use |
|------|---------|---------------|-------------|
| **Paper prototype** | Lowest | Concept clarity, information architecture | Very early — testing whether the idea makes sense |
| **Landing page** | Low | Demand — will people sign up? | Before building anything — test desirability |
| **Wizard of Oz** | Medium | Full experience without the technology | When the value depends on the experience, not the tech |
| **Concierge** | Medium | Value delivery manually | When you need to validate the service, not the tool |
| **Functional MVP** | Higher | Complete job completion with real users | When earlier validation passed and you need usage data |

### MVP Principles

1. **Gauge effort to degree of proof needed** — Don't build more than necessary to test the current riskiest assumption
2. **Ugly is fine** — Design fidelity should match the stage. At the MVP stage, a sketch or wireframe will do
3. **Observe behavior, not opinions** — Watch what people do with the MVP. "Would you use this?" is unreliable. "Here it is — try it" is reliable
4. **Time-box it** — An MVP that takes 3 months to build isn't minimum. If it takes more than 2-4 weeks, scope is too large
5. **Define what you'll learn** — Before building, state: "This MVP will tell us whether [assumption]. We'll know if [specific signal]"

---

## Two-Sided Markets

Products that serve two distinct user groups (Levy) require validating the value proposition for both sides:

| Side | Example (Airbnb) | Validation Need |
|------|------------------|-----------------|
| **Supply** | Hosts | Will hosts list properties? At what commission? With what support needs? |
| **Demand** | Guests | Will guests trust peer-to-peer accommodation? At what price? |
| **Platform** | Airbnb itself | Can we facilitate trust between strangers? Can we handle payments, disputes, safety? |

**Key insight:** You must solve the chicken-and-egg problem. Usually: start with one side (often supply) and use concierge or manual methods to serve the other until both sides reach critical mass.

The UX must address both sides, but it doesn't have to be equal. Start with the side that's harder to attract.
