# From Interviews to Insights: A Walkthrough

This example walks through the complete process of turning raw interview data into actionable design insights, using a fictional project: improving the onboarding experience for a project management tool called "TaskFlow."

---

## Context

**Study:** Generative research for TaskFlow onboarding redesign
**Method:** Semi-structured interviews (story-based)
**Participants:** 6 new users who signed up in the past 30 days
**Goal:** Identify why 55% of new users don't complete onboarding

---

## Step 1: Raw Interview Data

Here are excerpts from three of the six interviews:

### P1 — Sarah, Marketing Manager, 2 weeks in

> "I signed up because my boss told me to. I landed on this screen with like five options and I didn't know which one to pick. I think I clicked 'Create a project' but then it asked me all these questions about methodology — Kanban, Scrum, Waterfall — and I was like, I just want to make a to-do list."

> "I ended up closing the tab and going back to my spreadsheet. I came back a few days later when I had more time."

> "The thing is, I still don't really know what half the features do. I basically just use it as a list."

### P2 — Dev Lead, 3 weeks in

> "The setup was fine for me, I've used Jira and Asana before, so I knew what I was looking for. But when I tried to invite my team, I couldn't figure out where the invite function was. I went to Settings, then Project Settings, then back to the main page... turned out it was under the People icon in the sidebar."

> "My team members had an even harder time. Two of them asked me how to see their tasks. They couldn't find the board view."

### P3 — Freelance Designer, 1 week in

> "I almost didn't finish signing up because it asked for a company name and I don't have one. I just typed my name but it felt weird. The whole flow seemed designed for teams, not individuals."

> "I wanted to just track my client projects. I don't need sprints or retrospectives. I need deadlines and a way to share progress with clients."

---

## Step 2: Extract Observations

Write one observation per sticky note. Code each to its source participant.

| # | Observation | Source | Type |
|---|---|---|---|
| 1 | Felt overwhelmed by initial choices (5 options on first screen) | P1 | Barrier |
| 2 | Didn't understand project methodology options (Kanban/Scrum/Waterfall) | P1 | Barrier |
| 3 | Closed the tab and returned days later | P1 | Behavior |
| 4 | Uses the tool as a simple to-do list despite full feature set | P1 | Behavior |
| 5 | Doesn't understand what half the features do after 2 weeks | P1 | Barrier |
| 6 | Experienced user had no trouble with setup | P2 | Positive |
| 7 | Couldn't find the invite/People function (looked in Settings first) | P2 | Barrier |
| 8 | Team members couldn't find the board view | P2 | Barrier |
| 9 | "Company name" field felt wrong for solo user | P3 | Barrier |
| 10 | Entire flow felt designed for teams, alienating for individuals | P3 | Barrier |
| 11 | Doesn't need sprints/retrospectives — needs deadlines and client sharing | P3 | Goal |
| 12 | Signed up because boss told them to, not self-motivated | P1 | Context |

---

## Step 3: Group into Themes

After placing all sticky notes on the wall (from all 6 interviews), clusters emerge:

### Cluster A: "The onboarding assumes too much expertise"
- Observation 2: Didn't understand methodology options
- Observation 5: Doesn't understand features after 2 weeks
- [P4]: "I picked Kanban because it sounded familiar but I don't know what it means"
- [P5]: "The tutorial was about sprints and I don't use sprints"

### Cluster B: "Key features are hidden"
- Observation 7: Couldn't find invite function
- Observation 8: Team members couldn't find board view
- [P4]: "I didn't know there was a calendar view until my coworker showed me"
- [P6]: "Where do I add a deadline? I still haven't figured that out"

### Cluster C: "The product assumes you're a team, not an individual"
- Observation 9: "Company name" field wrong for solo users
- Observation 10: Flow designed for teams
- Observation 11: Needs deadlines and client sharing, not sprints
- [P5]: "I work alone, the collaboration features are just noise for me"

### Cluster D: "Users satisfice rather than explore"
- Observation 3: Closed tab, returned days later
- Observation 4: Uses as simple to-do list
- Observation 6: Experienced user had no trouble (prior mental model)
- [P6]: "I just picked the first option that seemed okay"

---

## Step 4: Write Insight Statements

Each cluster becomes an insight with three parts: observation, interpretation, and implication.

### Insight 1: Jargon-heavy onboarding creates a knowledge barrier

**Observation:** 4 of 6 participants didn't understand project methodology options (Kanban, Scrum, Waterfall) and couldn't distinguish between them. Two picked randomly; one abandoned.

**Interpretation:** The onboarding assumes domain knowledge that most non-technical users don't have. It forces a consequential decision (project methodology) at the moment of lowest understanding. This violates the principle that systems should match the user's language and mental model (Jakob's Law, Recognition over Recall).

**Implication:** Onboarding should defer methodology decisions or make them invisible. Ask users about their goals ("track tasks," "manage a team project," "share progress with clients") and map those to appropriate configurations behind the scenes.

**Severity:** High — directly causes abandonment
**Frequency:** High — 4 of 6 participants

---

### Insight 2: Core features lack discoverability

**Observation:** 5 of 6 participants couldn't find at least one key feature (inviting team members, board view, calendar view, deadlines). Users looked in logical places (Settings, Project Settings) but the features were elsewhere.

**Interpretation:** The information architecture doesn't match users' mental models for where features should live. The "People" icon in the sidebar is not a strong enough signifier for team management. Users default to Settings for anything configuration-related.

**Implication:** Add contextual discovery prompts within workflows (e.g., after creating a project, prompt "Want to invite team members?"). Consider restructuring Settings to include People and View options, or add clear labels to sidebar icons.

**Severity:** High — prevents core feature adoption
**Frequency:** High — 5 of 6 participants

---

### Insight 3: Solo users feel the product isn't for them

**Observation:** 2 of 6 participants were individual users. Both reported the onboarding felt designed for teams. The "Company name" field, collaboration-focused copy, and team methodology options created friction.

**Interpretation:** The product has a one-size-fits-all onboarding that optimizes for the team use case. Solo users represent a meaningful segment but are effectively alienated during first contact. This is a peak-end rule issue — the first impression shapes their entire relationship with the product.

**Implication:** Add a branching question early in onboarding: "Are you working solo or with a team?" Tailor subsequent screens, terminology, and default settings to match. For solo users: hide team features, use "your projects" instead of "workspace," and skip the company name field.

**Severity:** Moderate — doesn't cause abandonment but reduces engagement
**Frequency:** Moderate — 2 of 6 participants (but may represent a larger unseen segment)

---

### Insight 4: Users adopt the minimum viable workflow and stop exploring

**Observation:** 4 of 6 participants use only basic features (task lists) despite the product offering boards, timelines, calendars, and automations. They chose the first approach that worked and stuck with it.

**Interpretation:** This is classic satisficing behavior. Users don't explore because their immediate need is met. The product offers no progressive disclosure or contextual hints to guide users toward more powerful features once they're comfortable.

**Implication:** Implement progressive feature introduction — after users have been active for 1 week, surface contextual suggestions: "You have 15 tasks. Try Board View to see them visually." Avoid tooltip tours on day 1; time guidance to when it's relevant.

**Severity:** Moderate — doesn't prevent task completion but limits product value and retention
**Frequency:** High — 4 of 6 participants

---

## Step 5: Prioritize and Recommend

| Priority | Insight | Severity | Freq. | Tier | Recommendation | Effort |
|---|---|---|---|---|---|---|
| 1 | Jargon-heavy onboarding | High | High | 1 | Replace methodology picker with goal-based questions | Medium |
| 2 | Core features hidden | High | High | 1 | Add contextual prompts + relabel sidebar | Small |
| 3 | Solo users alienated | Moderate | Moderate | 2 | Add solo/team branching in onboarding | Medium |
| 4 | Users stop exploring | Moderate | High | 2 | Progressive feature introduction (week 1+) | Large |

---

## Step 6: Build the Opportunity Solution Tree

```
Desired Outcome: Increase onboarding completion from 45% to 75%
├── Users don't understand initial setup choices
│   ├── Replace methodology picker with goal questions
│   └── Offer guided templates based on role
├── Users can't find key features
│   ├── Add contextual discovery prompts
│   └── Restructure sidebar with labels
├── Solo users feel product isn't for them
│   └── Add solo/team path branching
└── Users adopt minimum workflow and stop
    ├── Progressive feature hints at day 7
    └── Usage-based suggestions ("You have 15 tasks...")
```

---

## What Made This Analysis Effective

1. **Started with stories, not opinions** — Interview questions asked about actual past behavior
2. **One observation per note** — Kept things atomic for flexible grouping
3. **Coded to participants** — Could trace every insight back to specific people
4. **Named clusters as insights, not topics** — "Jargon-heavy onboarding creates a knowledge barrier" vs. "Onboarding"
5. **Three-part insight format** — Observation → Interpretation → Implication provides clear logic chain
6. **Severity + frequency scoring** — Enables objective prioritization
7. **Connected to UX principles** — Referenced Jakob's Law, satisficing, peak-end rule to strengthen recommendations
8. **Ended with an OST** — Mapped insights directly to an actionable framework for the team
