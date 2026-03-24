# Persona Template

A persona is a fictional user archetype -- a composite model from research data that represents a group of needs and behaviors. This template covers all 12 persona elements defined in the analysis-synthesis reference, structured for markdown files with YAML frontmatter.

## When to Use

- Creating a new persona from research data (interviews, contextual inquiry, surveys)
- Extending an existing persona into a new product domain
- Validating that an existing persona covers all essential dimensions

## Before You Start

1. Review all relevant research data (interview transcripts, field notes, survey responses)
2. Identify behavioral variables for your domain (e.g., tech comfort, delegation level, decision-making style)
3. Map research participants along these variables to find clusters
4. Create one persona per behavioral cluster -- as few as possible while representing all relevant patterns
5. Flesh out using real data from participants in that cluster, not assumptions

## Template

```markdown
---
name: [First name -- natural for the demographic]
job: [Role / Title]
age: [Age]
tech stack: [Comma-separated tools and software they actually use]
tags: [primary | secondary]
---

## About

- Experience: [Years in role / industry, relevant career background]
- Education: [Degree, certification, or equivalent experience level]
- Company size: [Employees and/or revenue band]
- Industry segment: [Trade, specialty, or sub-sector]
- Work environment: [Office, field, hybrid, remote -- describe the physical context]

[2-3 paragraph narrative description. Write in third person. Cover: what they do day-to-day,
how they relate to the product domain, their workforce composition, and any contextual factors
that shape their behavior. Ground every claim in research data.]

## Quote

> "[A verbatim quote from interview data that embodies this persona's core belief or attitude.
> Use actual participant words, not paraphrased. The quote should immediately communicate
> who this person is and what they care about.]"

## Goals

- [Goal 1 -- what the product will help them achieve, written from their perspective]
- [Goal 2 -- use their vocabulary, not product jargon]
- [Goal 3 -- include both functional goals (get X done) and aspirational goals (become Y)]

## Challenges

- **[Challenge name]**: [Description grounded in observed behavior. What goes wrong? What is the consequence? Cite the source if useful -- e.g., "reported by 4 of 6 participants in this cluster."]
- **[Challenge name]**: [Description]
- **[Challenge name]**: [Description]

## Skills

- **Domain expertise**: [Low / Moderate / High -- how well they understand their industry's processes]
- **Technical proficiency**: [Low / Moderate / High -- comfort with software, digital tools]
- **Financial literacy**: [Low / Moderate / High -- understanding of accounting, payroll, compliance concepts]
- [Any other domain-relevant skill dimension]

## Behaviors and Habits

- [Habitual behavior 1 -- specific, observable, recurring. Use present tense. "Checks email and bank statements every morning before anything else."]
- [Habitual behavior 2 -- include workarounds, informal processes, and coping mechanisms]
- [Habitual behavior 3 -- note what they do vs. what they think they should do]

## Environment

- **Physical**: [Where they work -- office, job site, truck, home, hybrid. Describe the space.]
- **Technological**: [Devices, connectivity, software ecosystem. What's on their desk / in their pocket?]
- **Organizational**: [Company culture, decision-making norms, pace of work, level of formality]

## Relationships

- [Person/role 1 -- their relationship to this persona and how they influence decisions. E.g., "External CPA -- trusted advisor, dictates accounting platform, handles year-end taxes"]
- [Person/role 2 -- E.g., "Office manager -- executes payroll, first to notice errors, depends on persona for approvals"]
- [Person/role 3 -- E.g., "Field workers -- affected by payroll accuracy, limited technology access"]

## Motivations

- [What drives their behavior beyond task completion. Why do they get up in the morning?]
- [What would make them feel successful at the end of the week?]
- [What emotional need does the product serve -- control, safety, pride, independence?]

## Frustrations

- [Pain point 1 -- current-state friction. What makes them say "this is broken"?]
- [Pain point 2 -- use their words when possible, drawn from interview quotes]
- [Pain point 3 -- distinguish between surface frustration and root cause]

## Scenario

[A narrative that shows this persona encountering a trigger event, pursuing a goal, taking action,
and experiencing an outcome. Follow the scenario format:]

When [persona name] is [context/trigger], they want to [goal] so they [action sequence].
They feel [emotion] when [outcome].

[Write 3-5 sentences. The scenario should illustrate a realistic interaction with the product
domain -- not a happy path demo, but a moment of truth that reveals this persona's real needs.]
```

## Mapping to Existing Persona Files

If your project already has personas with a lighter structure, use this table to identify gaps:

| Template Element | Common Existing Section | Notes |
|---|---|---|
| About (narrative) | About this persona | Often bullet-only; add narrative paragraphs |
| Quote | *(often missing)* | Pull from interview transcripts |
| Goals | Goals | Usually present |
| Challenges | Challenges | Usually present |
| Skills | *(often missing)* | Critical for understanding product fit |
| Behaviors and Habits | Habits / Daily Activities | Consolidate into one section |
| Environment | *(often missing)* | Shapes technology adoption constraints |
| Relationships | *(often missing)* | Key for understanding influence and dependency |
| Motivations | *(often missing)* | Explains the "why" behind behaviors |
| Frustrations | *(sometimes merged with Challenges)* | Separate from Challenges -- frustrations are emotional, challenges are situational |
| Scenario | *(sometimes present)* | Essential for design validation |

## Quality Checklist

Before considering a persona complete:

- [ ] Every claim traces to a specific research source (interview, observation, survey)
- [ ] The persona represents a behavioral cluster, not a single participant
- [ ] Goals include both functional and aspirational dimensions
- [ ] Challenges distinguish between root causes and symptoms
- [ ] Skills section honestly assesses capability gaps (not flattering)
- [ ] Behaviors describe what they actually do, including workarounds
- [ ] Environment captures real constraints (connectivity, devices, workspace)
- [ ] Relationships identify who influences their decisions and who is affected by them
- [ ] Motivations explain why they care, not just what they do
- [ ] Frustrations use the persona's own vocabulary from research data
- [ ] Scenario follows the trigger-goal-action-emotion-outcome format
- [ ] The persona would be recognized as "real" by someone who works in this industry
- [ ] No emojis, no stock-photo language, no aspirational fiction
