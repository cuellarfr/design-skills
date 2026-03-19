---
name: ux-research
description: Plan, conduct, and analyze UX research using proven methodologies. Use when planning user research, writing interview scripts, creating test plans, recruiting participants, analyzing qualitative data, or synthesizing findings into actionable insights. Covers generative, evaluative, and continuous discovery research with specific frameworks, scoring rubrics, and templates.
---

# UX Research

Plan, conduct, and analyze user research that produces actionable insights for product design. This skill provides frameworks, methods, and practical guidance for every stage of the research process — from defining the right question to presenting findings that drive decisions.

## When to Use This Skill

Use this skill when:
- Planning a research study (choosing methods, defining scope, writing a plan)
- Writing interview scripts or discussion guides
- Creating usability test plans with tasks and success metrics
- Recruiting participants and writing screener surveys
- Analyzing qualitative data (affinity diagrams, thematic analysis)
- Synthesizing research into personas, journey maps, or opportunity maps
- Setting up continuous discovery practices (weekly interviews, OSTs)
- Presenting findings and recommendations to stakeholders

## Core Principle

Research is a tool for reducing risk, not a deliverable. The goal is always to inform decisions — not to produce documents. Research is not asking people what they like, not a political tool, and not science. It's applied inquiry that helps you solve the right problem.

## Research Types

Choose your research type based on what decisions are in play:

### Generative / Exploratory
**When:** Before you know what you're building. You need to define the problem.
**Methods:** Interviews, field observation, contextual inquiry, diary studies, literature review
**Output:** Problem definition, opportunity areas, personas, mental models

### Descriptive
**When:** You have a design problem and need to fully understand the context.
**Methods:** Contextual inquiry, fly-on-the-wall observation, journey mapping, card sorting
**Output:** Current-state maps, workflow diagrams, mental models

### Evaluative
**When:** You have potential solutions and need to test them.
**Methods:** Usability testing, heuristic evaluation, A/B testing, click testing, tree testing
**Output:** Severity-ranked issues, task completion rates, recommendations

### Causal
**When:** A solution is live and you need to understand actual usage patterns.
**Methods:** Analytics review, A/B testing, funnel analysis, surveys
**Output:** Conversion data, behavioral patterns, quantitative validation

## The Research Process

### 1. Define the Problem

Start with a clear problem statement. Base it on a verb that indicates outcome:
- **Good:** "Identify the barriers preventing users from completing onboarding"
- **Good:** "Evaluate whether the new checkout flow reduces abandonment"
- **Bad:** "Understand the user experience" (too vague)
- **Bad:** "Explore the problem space" (no measurable outcome)

Write 3-5 research questions. More than 10 means your scope is too broad.

### 2. Select the Approach

| You need to... | Use... | Time needed |
|---|---|---|
| Discover unmet needs | Generative interviews | 2-3 weeks |
| Understand context and workflows | Contextual inquiry | 1-2 weeks |
| Test a design concept | Usability testing | 3-5 days |
| Validate with numbers | Survey + analytics | 1-2 weeks |
| Quick expert review | Heuristic evaluation | 1-2 days |
| Prioritize features | Card sorting, buy-a-feature | 1 week |
| Understand navigation mental models | Tree testing, card sorting | 1 week |
| Track ongoing patterns | Continuous discovery (weekly) | Ongoing |

See `references/research-methods-catalog.md` for detailed method descriptions.

### 3. Plan and Prepare

Every study needs a written plan, even if it's brief. Use `templates/research-plan-template.md`.

**Essential plan elements:**
- Problem statement and research questions
- Methodology and rationale
- Participant criteria and recruiting approach
- Number of participants (see benchmarks below)
- Timeline and logistics
- How data will be captured and stored
- Who will participate from the team

**Participant benchmarks:**
- Usability testing: 3-5 per round (catch ~85% of issues with 5 users)
- Generative interviews: 5-8 per persona segment
- Card sorting: 15-20 for statistical patterns
- Surveys: 100+ for quantitative significance
- Continuous discovery: 1 per week minimum

### 4. Recruit Participants

Recruiting is the hardest part. Embrace it — good recruiting puts the quality in your research.

**A good participant:**
- Shares the goals and concerns of target users
- Embodies key characteristics (age, role, tech familiarity)
- Can articulate their thoughts clearly
- Is familiar with relevant technology at the same level as target users

**Write a screener survey** (see `templates/screener-template.md`):
- Define specific behaviors you're looking for
- Determine required tool knowledge and access level
- Set topic knowledge requirements
- Don't make it obvious who you're looking for (people will game it)

**Recruiting tips:**
- The importance of recruiting perfectly representative users is overrated
- Testing early and often matters more than perfect representation
- Don't be embarrassed to ask friends and neighbors for initial rounds
- Offer reasonable incentives ($50-100/hour)
- Keep the invitation simple
- Don't discuss the product beforehand

### 5. Collect Data

**Data management:**
- Use consistent naming: `Study-ParticipantName-YYYY-MM-DD`
- Get files onto a shared drive immediately
- Use familiar tools — technical difficulties kill research sessions
- Keep a research kit ready to go at a moment's notice

**Core collection methods:**

**Interviewing** — The most effective way to see the world as users do. See `references/interviewing-guide.md` for the full technique guide.

Quick checklist:
- Prepare an interview guide with goals, demographics, icebreakers, and focus questions
- Ask open-ended questions; follow up with "Tell me more about that"
- Listen more than you speak — get comfortable with silence
- Note exact phrases and vocabulary participants use
- Pay attention after you stop recording — revelations often come then

**Usability Testing** — Observe representative users attempting tasks with your design. See `references/usability-testing-guide.md` for the complete process.

Quick checklist:
- Create tasks based on scenarios and personas
- The designer should NOT be the facilitator
- Have a separate observer taking notes
- Test early, test often — never right before lunch
- 3 users per round, debrief over lunch the same day

**Contextual Inquiry** — Interview and observe in the participant's actual environment.

Quick checklist:
- Plan for travel time
- Get situated without interrupting routines
- Ask people to do activities, not give you a tour
- Observe everything: environment, workarounds, tools, interruptions
- Use more than one researcher for multiple perspectives

### 6. Analyze Data

Analysis is where patterns become insights. Get everyone involved — include people who will benefit from participating.

**Qualitative analysis process:**
1. Review all notes and recordings closely
2. Extract observations: behaviors, emotions, actions, verbatim quotes
3. Write each observation on a sticky note (coded to the source participant)
4. Group notes into themes on a whiteboard
5. Watch patterns emerge; rearrange as you assess
6. Name each cluster with an insight statement
7. Derive actionable recommendations from insights

**Analysis session structure:**
- Summarize research goals and process (what did we want to find out?)
- Describe participants and circumstances
- Describe data gathering methods
- Pull out quotes and observations as a group
- Group into themes (e.g., "participants rely on pen and paper to aid memory")
- Summarize findings: patterns → insights → implications for design
- Document in a shareable format

See `references/analysis-synthesis.md` for detailed techniques including affinity diagrams, opportunity mapping, and persona creation.

### 7. Report Results

A quick sketch of a persona or a photo of sticky notes on a whiteboard is far superior to a lengthy written report that goes ignored.

**Always include:**
- Research goals and questions
- Methods and participant summary
- Key findings (patterns and insights)
- Severity-ranked recommendations
- Suggested next steps

**Findings severity scale:**

| Severity | Definition | Action |
|---|---|---|
| **Critical** | Prevents users from completing the task entirely | Must fix before release |
| **High** | Causes significant difficulty; users may abandon | Fix in current cycle |
| **Moderate** | Causes some difficulty but users can work around it | Plan for next cycle |
| **Low** | Minor friction; cosmetic or preference-based | Add to backlog |

**Findings frequency scale:**

| Frequency | Definition |
|---|---|
| **High** | 30%+ of participants experienced the problem |
| **Moderate** | 11-29% of participants experienced the problem |
| **Low** | 10% or fewer participants experienced the problem |

**Issue triage (3 tiers):**
- **Tier 1:** High severity + high frequency → immediate action, high risk to product success
- **Tier 2:** Moderate severity with low frequency, or low severity with moderate frequency
- **Tier 3:** Low severity + low frequency → low risk, add to backlog

Use `templates/findings-report-template.md` for the report structure.

## Continuous Discovery

For teams practicing continuous discovery (recommended), research is not a phase — it's a weekly habit.

**The continuous discovery cadence:**
- Weekly touchpoints with customers by the team building the product
- Small research activities in pursuit of a desired outcome
- Infuse daily product decisions with continuous customer input

**The product trio** (product manager + designer + engineer) should:
- Conduct story-based interviews weekly (not opinion-based — ask about actual past behavior)
- Maintain an Opportunity Solution Tree mapping outcomes → opportunities → solutions → assumption tests
- Generate 15-20 solution ideas per opportunity (volume drives quality)
- Test 10-20 assumptions per week through small, rapid experiments
- Define success criteria before running tests

See `references/continuous-discovery.md` for the full framework.

## Common Mistakes to Avoid

- **Leading questions:** "Don't you think this is easier?" → "How would you describe this experience?"
- **Confirmation bias:** Seeking evidence that supports your hypothesis instead of genuinely testing it
- **Testing too late:** Testing right before launch when there's no time to act on findings
- **Asking opinions instead of observing behavior:** People don't accurately predict their own behavior
- **Over-documenting, under-acting:** A 50-page report nobody reads vs. a whiteboard photo that drives change
- **Skipping the screener:** Recruiting anyone available instead of representative participants
- **The facilitator is the designer:** The person who built it can't objectively watch it fail
- **Solving during analysis:** Resist the urge to jump to solutions before the patterns are clear
- **Adding features based on user requests:** "I'd like it if it could do X" — probe deeper; they often already have a source for X

## Quick Reference

**Problem statement formula:** `[Verb: identify/evaluate/determine] + [what] + [for whom] + [context]`
**Interview question format:** Open-ended, behavior-focused, past-tense ("Tell me about the last time you...")
**Usability task format:** Scenario-based, goal-oriented ("You want to [goal]. Show me how you'd do that.")
**Screener format:** Behavioral questions that filter without revealing criteria
**Analysis output:** Pattern → Insight → Recommendation → Severity

## Resources

This skill includes:
- **references/research-methods-catalog.md**: Detailed guide to 20+ research methods organized by type
- **references/interviewing-guide.md**: Complete interviewing technique from preparation to debrief
- **references/usability-testing-guide.md**: Full testing process with scoring rubrics, triage, SUS (full 10-question scale with scoring formula, grade/percentile interpretation, subscales), and alternative questionnaires (UMUX-Lite, SEQ, NASA-TLX)
- **references/analysis-synthesis.md**: Affinity diagrams, thematic analysis, persona creation, opportunity mapping
- **references/continuous-discovery.md**: Weekly cadence, Opportunity Solution Trees, assumption testing
- **references/workshop-methods.md**: Team facilitation techniques — problem framing (HMW, Problem Tree, Abstraction Laddering, Rose/Thorn/Bud), ideation (Thumbnail Sketching, Creative Matrix, Round Robin, Alternative Worlds), prioritization (Importance/Difficulty Matrix, Bull's-Eye, Dot Voting, What's on Your Radar), and modeling (Storyboarding, Concept Poster, Cover Story Mock-Up). Includes half-day workshop template and facilitation anti-patterns.
- **templates/research-plan-template.md**: Fillable research plan
- **templates/interview-guide-template.md**: Interview script template
- **templates/usability-test-plan-template.md**: Test plan with tasks and metrics
- **templates/screener-template.md**: Participant screener survey
- **templates/findings-report-template.md**: Research findings report
- **examples/method-selection-scenarios.md**: "Given X situation, use Y method" decision guide
- **examples/interview-to-insights.md**: Walkthrough from raw interview data to actionable insights
