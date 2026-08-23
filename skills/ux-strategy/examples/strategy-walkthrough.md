# Strategy Walkthrough

End-to-end UX strategy for a fictional B2B product — from framing through measurement.

---

## Context

**Product:** TaskFlow — a mid-stage project management SaaS for small agencies (10-50 people)
**Situation:** TaskFlow has 2,000 paying customers but trial-to-paid conversion has stalled at 4%. Leadership wants to reach 8%. The product trio is tasked with improving conversion.
**Team:** PM (Dana), Designer (Marcus), Engineer (Priya)

---

## Phase 1: Frame

### Setting the Outcome

**Business outcome (from leadership):** Increase monthly recurring revenue (MRR)
**Product outcome (proposed by trio):** Increase trial-to-paid conversion from 4% to 8%

The trio pushed back on "increase MRR" as a product outcome — it's a lagging business metric the trio can't directly influence. Trial-to-paid conversion is a leading indicator they can design for.

**Outcome type:** Performance goal (they have 6 months of baseline data showing consistent 4%).

### Constraints

| Constraint | Detail |
|-----------|--------|
| Timeline | Q3 (12 weeks) |
| Resources | One product trio, 70% allocation (remaining 30% on maintenance) |
| Technical | Must work within existing tech stack. No new infrastructure |
| Business | Can't change pricing — pricing review is a separate initiative |

---

## Phase 2: Discover

### Customer Interviews

The trio committed to **two interviews per week** for 4 weeks. They targeted three segments:

- Users who **converted** (signed up, paid) — what worked?
- Users who **churned during trial** — what failed?
- Users who are **still in trial** — what are they evaluating?

**Recruiting:** In-product intercept on day 5 of trial ("Would you chat with our product team for 20 minutes? $25 gift card").

### Interview Approach

Story-based interviewing (Torres). Key questions:
- "Tell me about the last time you were evaluating a new tool for your team."
- "Walk me through what happened from when you first signed up for TaskFlow."
- "Tell me about a moment when you almost gave up on the trial."

### Key Findings (after 8 interviews)

**From churned trial users:**
1. "I signed up but couldn't figure out how to set up a project the way my team actually works" — 5/8 mentioned this
2. "I imported my data from [competitor] but it came in wrong and I couldn't fix it" — 3/8
3. "I couldn't get my team to try it because they'd have to learn a whole new system" — 4/8
4. "I realized I'd need to set up everything myself and I don't have time for that" — 6/8

**From converted users:**
1. "I got lucky — a colleague showed me how they set it up and I copied their approach" — 3/4
2. "The templates got me 80% there, but I had to customize a lot" — 2/4
3. "Once my team saw the dashboard, they got it immediately" — 3/4

**From active trial users:**
1. "I'm still trying to figure out if this can replace what we have. I haven't set up a real project yet" — 2/3
2. "I keep comparing it to [competitor] and I can't tell if it's better yet" — 2/3

### Experience Map

The trio individually mapped the trial experience, then merged:

```
Sign up → Land on empty dashboard → Try to create a project →
Get stuck on project structure → Look for help → Find templates →
Templates don't match my workflow → Try to customize → Get confused →
Give up OR persist → Eventually set up one project → Invite team →
Team ignores invite OR team tries it → Dashboard starts showing value →
Convert OR churn
```

**Critical insight:** The gap between "sign up" and "first project that works for my team" is where most users drop off. The product delivers value once configured, but configuration is the bottleneck.

---

## Phase 3: Opportunity Mapping

### Opportunity Solution Tree

```
Outcome: Increase trial-to-paid conversion (4% → 8%)
│
├── When I first sign up
│   ├── I land on an empty screen and don't know where to start
│   └── I can't tell what the product can do for me
│
├── When I try to set up my first project
│   ├── The project structure doesn't match how my team works ← TARGET
│   ├── I have to configure everything from scratch — too much effort
│   ├── Templates exist but none match my agency type
│   └── I imported data from my old tool but it mapped incorrectly
│
├── When I try to get my team to adopt
│   ├── My team has to learn a whole new system
│   ├── I can't show my team the value until everything is set up
│   └── Team invitations don't explain why they should care
│
└── When I'm evaluating whether to pay
    ├── I haven't used it enough to know if it's better than what I have
    └── I can't tell what I'd lose on the free tier
```

### Prioritized Opportunity

**Selected:** "The project structure doesn't match how my team works"

| Dimension | Assessment |
|-----------|-----------|
| Sizing | 5/8 churned users mentioned this. Affects every trial user |
| Severity | High — users can't progress without solving this. No effective workaround |
| Company alignment | Core to the product's value. Solving this helps all segments, not just trial |
| Market factors | Competitors offer rigid templates. Flexible setup could differentiate |

---

## Phase 4: Competitive Analysis

### Quick Competitive Scan

| Competitor | Onboarding Approach | Customization | Time to First Project |
|-----------|-------------------|---------------|----------------------|
| Asana | Template gallery + blank project | High flexibility, low guidance | 5-15 minutes (but often misconfigured) |
| Monday.com | Interactive template wizard | Template-based with modifications | 3-10 minutes |
| Basecamp | Opinionated defaults, minimal config | Low flexibility, high speed | 2-5 minutes |
| ClickUp | Feature-rich setup with many options | Very high flexibility, overwhelming | 15-30 minutes |

**Gap identified:** No competitor asks "What kind of work does your team do?" and then **configures the project structure automatically**. Everyone either provides templates (user picks and customizes) or blank canvases (user builds from scratch).

### Value Innovation

| Action | Decision |
|--------|----------|
| **Eliminate** | Blank project option during trial (too much cognitive load for new users) |
| **Reduce** | Number of templates shown (from 40 to 5 agency-specific ones) |
| **Raise** | Template relevance — match to the user's specific agency type and workflow |
| **Create** | "Tell us about your team" onboarding flow that generates a configured project |

---

## Phase 5: Ideation and Validation

### Three Solutions

**Solution A — Guided Setup Interview:** A 5-question conversational flow during onboarding: "What does your agency do?" → "How many active projects?" → "How does work flow through your team?" → Auto-generates a configured project with realistic sample data.

**Solution B — Live Template Preview:** Instead of template thumbnails, show a fully populated preview of each template. User can click through and see what their project would look like with real data before committing.

**Solution C — Copy a Colleague:** If a team member invites them, the new user starts with a copy of the inviter's project structure. Reduces setup to zero for team members.

### Assumption Testing

**Solution A — Guided Setup Interview:**

| Assumption | Type | Test | Success Criteria | Result |
|-----------|------|------|-----------------|--------|
| Users will answer 5 onboarding questions (won't abandon) | Usability | Prototype test with 10 trial users | 7/10 complete all 5 questions | **8/10 completed** — Pass |
| Auto-generated project matches user's workflow well enough to use | Desirability | Same prototype test — ask "Would you start working in this project?" | 6/10 say yes | **7/10 said yes** — Pass |
| We can generate useful project structures from 5 answers | Feasibility | Engineering spike — can we map answer combinations to templates? | Cover 80% of agency types | **85% coverage** — Pass |

**Solution B — Live Template Preview:**

| Assumption | Type | Test | Success Criteria | Result |
|-----------|------|------|-----------------|--------|
| Users can evaluate a template from a populated preview | Usability | Click test — show 3 populated previews, ask users to pick the best fit | 7/10 pick the correct one for their agency type | **5/10 correct** — Fail (previews too complex to scan quickly) |

**Solution C — Copy a Colleague:**

| Assumption | Type | Test | Success Criteria | Result |
|-----------|------|------|-----------------|--------|
| Most trial users are invited by someone (not signing up alone) | Desirability | Data mining — % of trial signups that came from a team invite | >50% from invites | **28% from invites** — Fail (most sign up independently) |

### Decision

Solution A validated across all three assumptions. Solutions B and C had critical failures. The trio commits to building Solution A — the Guided Setup Interview.

---

## Phase 6: Measure

### Metrics

| Metric | Baseline | Target | Timeframe |
|--------|---------|--------|-----------|
| **Trial-to-paid conversion** (North Star for this initiative) | 4% | 8% | 12 weeks post-launch |
| Onboarding completion rate | 35% | 65% | 4 weeks post-launch |
| First project created within 24 hours | 18% | 50% | 4 weeks post-launch |
| Team members invited within 7 days | 22% | 35% | 8 weeks post-launch |

### Instrumentation

Events tracked:
- `onboarding_started` — User begins guided setup
- `onboarding_question_answered` (with question number) — Progress through flow
- `onboarding_completed` — All 5 questions answered
- `onboarding_abandoned` (with last question) — Where users drop off
- `project_auto_generated` — System creates the project
- `project_first_edit` — User modifies the generated project (signal of engagement)
- `team_invite_sent` — User invites team members

Cohort comparison: Users who go through guided setup vs. users who skip to manual setup (escape hatch preserved for power users).

### Results (8 weeks post-launch)

| Metric | Baseline | Target | Actual |
|--------|---------|--------|--------|
| Trial-to-paid conversion | 4% | 8% | 6.5% |
| Onboarding completion | 35% | 65% | 71% |
| First project within 24 hours | 18% | 50% | 58% |
| Team invites within 7 days | 22% | 35% | 31% |

**Analysis:** Conversion improved significantly (4% → 6.5%) but didn't reach the 8% target. The funnel data reveals: onboarding and project creation improved beyond targets, but the drop-off now occurs between "project created" and "team adoption." The bottleneck has shifted.

**Next cycle:** The trio returns to the OST and pivots to the "When I try to get my team to adopt" branch — specifically "I can't show my team the value until everything is set up." The guided setup solved the individual setup problem, but team adoption remains the next opportunity.

---

## Key Takeaways

1. **The outcome negotiation prevented wasted effort** — "Increase MRR" would have led the trio in a dozen directions. "Increase trial-to-paid conversion" focused the work
2. **Interviews revealed the real problem** — The team assumed trial churn was a pricing issue. It was a setup friction issue
3. **Three solutions prevented premature commitment** — Solution B and C seemed promising but failed critical assumptions
4. **Small, fast tests saved months** — The prototype test for Solution A took 3 days. Building the wrong solution would have taken 6 weeks
5. **Measurement revealed the next opportunity** — Hitting the target on intermediate metrics but not the final one showed exactly where the funnel still leaks
6. **Discovery is continuous** — The team didn't "finish" strategy. They completed one cycle and started the next
