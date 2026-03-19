# Method Selection Scenarios

Real-world scenarios showing how to choose the right research method. For each situation, we explain the decision rationale and the expected output.

---

## Scenario 1: "We're building a new product and don't know where to start"

**Context:** The team has a vague idea about the problem space but hasn't talked to users yet. Stakeholders have opinions about what to build, but no evidence.

**Research type:** Generative / Exploratory

**Recommended methods:**
1. **Stakeholder interviews** (first) — Understand business goals, constraints, and internal assumptions
2. **User interviews** (5-8 per segment) — Discover real needs, goals, and pain points
3. **Contextual inquiry** (3-5 sessions) — Observe actual behavior in context

**Why not usability testing?** There's nothing to test yet. You need to understand the problem before designing solutions.

**Expected output:** Personas, opportunity map, problem statement, design principles

**Timeline:** 3-4 weeks

---

## Scenario 2: "We redesigned the navigation and need to know if it works"

**Context:** The IA team restructured the site navigation based on card sort results. They have a prototype and want to validate before development.

**Research type:** Evaluative

**Recommended methods:**
1. **Tree testing** (20-30 participants) — Validate findability in the new structure without visual design influence
2. **Usability testing** (5 users) — Test the prototype with realistic task scenarios

**Why tree testing before usability testing?** Tree testing isolates the IA from visual design. If items are unfindable in the tree, no amount of visual polish will fix it.

**Expected output:** Findability scores per task, completion rates, identified problem areas in the hierarchy

**Timeline:** 1-2 weeks

---

## Scenario 3: "Users are dropping off during onboarding but we don't know why"

**Context:** Analytics show 60% of new users abandon during onboarding. The team has hypotheses but no direct user data.

**Research type:** Evaluative + Generative (combined)

**Recommended methods:**
1. **Analytics review** (first) — Identify exactly where users drop off (which step, which screen)
2. **Usability testing** (5 users) — Watch new users go through onboarding; identify confusion points
3. **Post-abandonment interviews** (5-8 users who dropped off) — Understand why they left in their own words

**Why not just A/B testing?** A/B testing tells you which version performs better, but not why users are struggling. You need to understand the problem before testing solutions.

**Expected output:** Step-by-step drop-off analysis, severity-ranked issues, recommendations for each onboarding step

**Timeline:** 2-3 weeks

---

## Scenario 4: "The team is arguing about which feature to build next"

**Context:** Product and engineering have different opinions about priorities. There's no user data to settle the debate.

**Research type:** Generative

**Recommended methods:**
1. **User interviews** (5-8) focused on current workflows and pain points
2. **Buy a Feature** exercise with 4-8 users — Force trade-off decisions to reveal true priorities
3. **Opportunity Solution Tree** — Map interview findings to a structured framework for prioritization

**Why not a survey?** Surveys tell you what people say they want. Interviews + Buy a Feature reveal what they actually need and what they'll trade off.

**Expected output:** Prioritized opportunity map, evidence-based feature recommendations

**Timeline:** 2 weeks

---

## Scenario 5: "We need quick feedback on two design directions"

**Context:** The team has two competing design concepts for a key flow. They need to decide which direction to pursue before investing in a full prototype.

**Research type:** Evaluative

**Recommended methods:**
1. **Comparative usability testing** (5 users) — Show both concepts to the same users in alternating order; ask them to complete the same tasks on each
2. **Preference testing** (after tasks) — Ask which they preferred and why

**Why not A/B testing?** The designs aren't built yet. Comparative usability testing is faster and cheaper at this stage, and you get qualitative data about why one works better.

**Expected output:** Task completion comparison, qualitative preference data, clear recommendation for which direction to pursue

**Timeline:** 3-5 days

---

## Scenario 6: "We launched 3 months ago and want to know how it's going"

**Context:** The product is live with real users. The team wants to understand adoption patterns, satisfaction, and areas for improvement.

**Research type:** Causal + Evaluative

**Recommended methods:**
1. **Analytics review** — Understand actual usage patterns, feature adoption, retention
2. **Survey** (100+ users) — Measure satisfaction (SUS, NPS), identify top pain points at scale
3. **Follow-up interviews** (5-8 from survey respondents) — Deep dive into the "why" behind survey patterns

**Why not just analytics?** Analytics tell you what users do, not why. The survey adds breadth; interviews add depth.

**Expected output:** Usage report, satisfaction benchmarks, prioritized improvement roadmap

**Timeline:** 3-4 weeks

---

## Scenario 7: "We need to understand how our product fits into users' daily workflow"

**Context:** The team knows users interact with their product alongside many other tools, but doesn't understand the full workflow context.

**Research type:** Descriptive

**Recommended methods:**
1. **Contextual inquiry** (5-8 sessions) — Visit users in their environment; watch them work
2. **Diary study** (10-15 users, 1-2 weeks) — Capture daily tool usage and context over time
3. **Journey mapping** (synthesis) — Visualize the full workflow with touchpoints, emotions, and pain points

**Why contextual inquiry instead of interviews?** People can't accurately describe their workflow from memory. You need to observe it happening.

**Expected output:** Current-state journey map, workflow diagram, integration opportunities

**Timeline:** 3-5 weeks

---

## Scenario 8: "We're setting up continuous discovery for the first time"

**Context:** The team wants to move from ad-hoc research to weekly customer touchpoints.

**Recommended setup:**
1. **Automate recruiting** — Add in-product prompts for research participation
2. **Weekly story-based interviews** (1 per week minimum) — Focus on actual past behavior
3. **Maintain an OST** — Update weekly with new opportunities from interviews
4. **Run assumption tests** — 2-3 small experiments per week
5. **Monthly synthesis** — Step back and look for patterns across the month's interviews

**Start small:** Even one interview per week is infinitely better than quarterly research. Build the habit first, then scale.

**Timeline:** Ongoing — expect 4-6 weeks to establish the rhythm

---

## Quick Decision Matrix

| Situation | Start here | Then consider |
|---|---|---|
| Don't know the problem | User interviews | Contextual inquiry |
| Know the problem, exploring solutions | Usability testing (prototype) | Comparative testing |
| Validating information architecture | Tree testing, card sort | Usability testing |
| Measuring live product | Analytics + survey | Follow-up interviews |
| Settling internal debates | User interviews + Buy a Feature | Opportunity mapping |
| Quick design feedback | Usability testing (3 users) | Same-day iteration |
| Understanding full context | Contextual inquiry | Diary study + journey map |
| Establishing ongoing practice | Weekly interviews | OST + assumption testing |
