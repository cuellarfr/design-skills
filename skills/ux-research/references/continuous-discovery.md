# Continuous Discovery

A framework for integrating research into weekly product development practice, based on established continuous discovery and Lean UX principles.

## Why Continuous Discovery?

Digital products are never finished. Customer needs and market conditions change continuously. Research cannot be a phase — it must be a habit. The goal: weekly touchpoints with customers by the team building the product, conducting small research activities in pursuit of a desired outcome.

## The Product Trio

Continuous discovery is driven by a **product trio**: product manager + designer + engineer. All three participate in:
- Customer interviews
- Opportunity mapping
- Solution ideation
- Assumption testing

This isn't optional. Cross-functional participation ensures solutions are desirable, viable, and feasible from the start.

## Six Prerequisite Mindsets

1. **Outcome-oriented:** Define success by impact on customers and business, not by features shipped
2. **Customer-centric:** Place the customer at the center; prioritize their needs alongside business needs
3. **Collaborative:** Reject siloed work; leverage collective expertise
4. **Visual:** Use drawings, maps, and diagrams to externalize thinking
5. **Experimental:** Adopt a scientific approach — identify assumptions and test them
6. **Continuous:** Move away from project mindset; integrate discovery throughout development

## The Weekly Cadence

### Minimum Viable Discovery

| Activity | Frequency | Time |
|---|---|---|
| Customer interview | Weekly | 30-60 min |
| Interview snapshot synthesis | After each interview | 15 min |
| Opportunity Solution Tree update | Weekly | 30 min |
| Assumption identification | Per solution idea | 30 min |
| Assumption test (small experiment) | 2-3 per week | Varies |

### Automating Recruiting

The biggest barrier to weekly interviews is recruiting. Automate it:
- **In-product prompts:** "Help us improve — chat with our team for 15 min"
- **Post-interaction surveys** with opt-in for follow-up
- **Customer success team** referrals
- **Maintain a participant panel** with a simple sign-up form
- **Incentivize participation** with gift cards, early access, or product credits

## The Opportunity Solution Tree (OST)

The central visual framework for continuous discovery. It maps the path from a desired outcome to testable assumptions.

### Structure

```
Desired Outcome
├── Opportunity A (customer need/pain/desire)
│   ├── Sub-opportunity A1
│   │   ├── Solution 1
│   │   │   ├── Assumption test
│   │   │   └── Assumption test
│   │   └── Solution 2
│   └── Sub-opportunity A2
│       └── Solution 3
├── Opportunity B
│   ├── Solution 4
│   └── Solution 5
└── Opportunity C
    └── Solution 6
```

### Building the OST

**Step 1 — Set the desired outcome:**
- Must be a product outcome (metric the team can directly influence)
- Not a business outcome (lagging indicator like revenue)
- Example: "Increase weekly active users who complete onboarding from 40% to 65%"

**Step 2 — Map the opportunity space:**
- Opportunities come from customer interviews — they are needs, pain points, and desires
- Structure opportunities hierarchically (big problems → sub-problems)
- Break down until opportunities are specific enough to address with a single solution
- Target "leaf nodes" — opportunities with no children

**Step 3 — Ideate solutions:**
- Generate 15-20 ideas per target opportunity (volume drives quality)
- Use group evaluation (dot-voting) to select ~3 diverse solutions for further exploration
- Don't converge too early — diversity of solutions is important

**Step 4 — Identify assumptions:**
- For each solution, enumerate what must be true for it to work
- Categories: desirability, viability, feasibility, usability, ethical
- Use story mapping and pre-mortems to surface hidden assumptions

**Step 5 — Test assumptions:**
- Prioritize "leap of faith" assumptions (riskiest ones)
- Use assumption mapping: plot assumptions on importance vs. certainty
- Test the riskiest, most important assumptions first

## Story-Based Interviewing

The backbone of continuous discovery. Collect stories about actual past behavior, not opinions about hypothetical futures.

### Why Stories?

- People don't accurately predict their own future behavior
- Stories reveal actual behavior, context, emotions, and workarounds
- Stories surface opportunities you wouldn't think to ask about
- Stories are harder to fabricate than opinions

### Interview Structure for Continuous Discovery

**Opening (5 min):**
> "Tell me about the last time you [did relevant activity]."

**Story collection (20-30 min):**
- Follow the story chronologically: "What happened next?"
- Dig into key moments: "Tell me more about that."
- Capture emotions: "How did that make you feel?"
- Understand motivation: "Why was that important to you?"
- Explore alternatives: "What did you try before that?"

**Closing (5 min):**
- "Is there anything else about this experience you'd like to share?"
- Thank them and explain how their input will be used

### Interview Snapshot

After each interview, create a quick-reference summary:

- **Participant:** Name/ID, role, key demographics
- **Date:** Date of interview
- **Stories collected:** 1-2 sentence summary of each story shared
- **Opportunities identified:** Needs, pain points, desires surfaced
- **Memorable quotes:** 2-3 verbatim quotes
- **Surprises:** Anything unexpected or that challenged assumptions

### Synthesizing Across Interviews

After every 3-5 interviews:
1. Review all interview snapshots
2. Look for patterns across stories
3. Add new opportunities to the OST
4. Refine or restructure existing opportunities
5. Identify which opportunities are growing in evidence

## Assumption Testing

### Types of Assumptions

| Type | Question it answers | Example |
|---|---|---|
| **Desirability** | Do customers want this? | "Users will prefer self-service onboarding over guided setup" |
| **Viability** | Can the business sustain this? | "This feature won't increase support costs beyond $X/month" |
| **Feasibility** | Can we build this? | "We can integrate with the payment API within one sprint" |
| **Usability** | Can users figure it out? | "Users can complete checkout in under 3 minutes" |
| **Ethical** | Should we build this? | "This feature won't create dark patterns or manipulate users" |

### Assumption Mapping

Plot assumptions on a 2x2:

```
         Important
            │
    Test     │    Test
    these    │    these
    SECOND   │    FIRST
            │
  ──────────┼──────────
            │
    Don't    │    Test
    test     │    these
    these    │    THIRD
            │
         Unimportant

   Known ◄──┼──► Unknown
```

### Designing Tests

**Principles:**
- Test assumptions, not whole ideas
- Define success criteria BEFORE running the test
- Design the smallest possible experiment
- Simulate an experience to evaluate actual behavior (not stated preference)
- Aim for 10-20 iterations per week

**Test types (from fastest to most rigorous):**

| Test | Speed | Fidelity | Best for |
|---|---|---|---|
| Smoke test (fake door) | Hours | Low | Desirability — would users click? |
| Concierge test | Days | Medium | Process — can we deliver value manually? |
| Wizard of Oz | Days | Medium | Feasibility — does the concept work? |
| Prototype test | Days | Medium-High | Usability — can users complete the task? |
| A/B test | Weeks | High | Optimization — which version performs better? |
| Pilot / Beta | Weeks | High | Full validation before broad rollout |

## Integrating with Agile

### Dual-Track Agile

- **Discovery track:** Testing hypotheses, talking to users, mapping opportunities
- **Delivery track:** Building the ideas that survive discovery
- Some team members participate in both tracks
- Discovery feeds the delivery backlog with validated ideas

### Sprint Integration

1. **Start of sprint:** Review OST, select target opportunity
2. **During sprint:** Run 1-2 interviews + 2-3 assumption tests
3. **End of sprint:** Update OST with new evidence, share findings at retro
4. **Continuous:** Discovery data informs delivery priorities

### Communicating with Stakeholders

- **Show the OST:** It makes your decision logic visible
- **Share interview snapshots:** Quick, digestible evidence
- **Present assumption test results:** "We tested X, here's what we learned"
- **Frame everything in outcomes:** "This will move [metric] because [evidence]"

## Common Pitfalls

- **Interviewing without a desired outcome:** You'll collect interesting but unfocused data
- **Jumping to solutions before mapping opportunities:** You'll solve the wrong problem
- **Testing whole ideas instead of assumptions:** Too slow, too expensive
- **Skipping the weekly cadence:** Discovery debt accumulates like technical debt
- **Only the PM does interviews:** The whole trio needs direct customer contact
- **Treating the OST as static:** It should evolve weekly as you learn
