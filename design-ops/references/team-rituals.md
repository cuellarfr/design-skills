# Team Rituals and Cadences

Deep reference for design team rituals — critiques, syncs, reviews, retros, and how they fit together into a sustainable cadence.

---

## Design Critique

The most important ritual for design quality. Done well, critique raises the bar for everyone. Done poorly, it becomes a political approval gate or an awkward silence.

### Critique Format

**Duration:** 45-60 minutes
**Frequency:** Weekly (same day, same time — never skip)
**Attendees:** All designers. Optional: PM, engineering lead, content strategist

**Structure:**

| Phase | Time | Activity |
|-------|------|----------|
| **Setup** | 2 min | Presenter shares screen, states what they're working on and what feedback they need |
| **Silent review** | 3 min | Everyone reviews the work silently. No talking. Write observations on stickies or in chat |
| **Feedback round** | 15-20 min | Each person shares one observation at a time. Go around the table. Facilitator captures themes |
| **Discussion** | 5-10 min | Open discussion on the thorniest issues. Presenter can ask clarifying questions |
| **Next steps** | 2 min | Presenter summarizes what they'll change. Facilitator captures action items |
| **Repeat** | — | Next presenter (2-3 pieces per session) |

### Critique Rules

1. **Presenter frames the request.** "I'm working on the checkout flow. I'm confident about the layout but struggling with the payment method selection. Focus your feedback there." This prevents unfocused scatter-shot feedback
2. **Feedback references principles.** "Hick's Law suggests fewer options. You have 6 payment methods visible at once — could you group or default?" Not "I think there are too many options"
3. **Problems, not solutions.** "The hierarchy between the primary and secondary actions is unclear." Not "Make the primary button bigger." The presenter solves the problem
4. **No defending.** The presenter listens and asks questions. Not "But the stakeholder said..." or "I already tried that"
5. **Written capture.** Every feedback item is written down with an owner. If it's not captured, it didn't happen
6. **Kindness is not silence.** Saying nothing about a real issue is not kind — it lets the problem ship. Kind feedback is honest, specific, and constructive

### Critique Anti-Patterns

| Anti-Pattern | Symptom | Fix |
|-------------|---------|-----|
| **The approval gate** | People present finished work looking for sign-off, not feedback | Only present work-in-progress. If it's done, it's too late for critique |
| **The pile-on** | Everyone gives the same feedback, presenter feels attacked | Facilitator groups similar feedback. One person states it, others +1 |
| **The silence** | Nobody says anything. Presenter assumes the work is perfect | Facilitator calls on people. Use "What's one thing you'd change?" |
| **The redesign** | Feedback becomes a collaborative redesign session in real-time | "That's a solution. What's the problem you're seeing?" Redirect to problems |
| **The seniority show** | Most senior person speaks first, others agree | Senior people speak last. Or use anonymous written feedback first |
| **The bikeshed** | 20 minutes on icon color, 0 minutes on the interaction model | Facilitator redirects: "Let's focus on the structural feedback the presenter asked for" |

### Critique Variations

| Format | When to Use |
|--------|------------|
| **Standard critique** | Regular weekly session. 2-3 presenters, 15-20 min each |
| **Deep dive** | One presenter, full session (45 min). Complex feature, major decision |
| **Speed critique** | 5 presenters, 8 min each. Quick feedback on smaller pieces |
| **Pair critique** | Two designers review each other's work. Daily or ad-hoc. Low overhead |
| **Cross-team critique** | Invite designers from another team. Fresh perspectives, consistency check |
| **Async critique** | Presenter shares a Loom video + Figma link. Team leaves written comments within 24 hours. For remote teams in different time zones |

---

## Design-Engineering Sync

The bridge between design and engineering. Prevents surprises.

### Sync Structure

**Duration:** 30 minutes
**Frequency:** Weekly
**Attendees:** Design lead + engineering lead (or tech lead). Full team for complex topics.

**Agenda:**

| Phase | Time | Purpose |
|-------|------|---------|
| **This sprint** | 10 min | Status of designs currently being built. Any questions or blockers from engineering |
| **Next sprint** | 10 min | Preview upcoming designs. Feasibility gut-checks. Flag anything that needs research |
| **Design QA** | 5 min | Review any open design QA issues. Prioritize fixes |
| **Open items** | 5 min | Anything else — technical constraints, new patterns, design debt |

### What to Cover

- **Engineering constraints the designer needs to know:** API limitations, performance budgets, platform differences, library capabilities
- **Design decisions the engineer needs to know:** Why this approach, not that one. What matters most vs. what's flexible
- **Component reuse:** Is there an existing component? Does a new one need to be built? Does the design system need updating?
- **Scope negotiation:** What can be simplified without losing the core experience? What can be deferred?

---

## Design Review

Stakeholder alignment on design direction. Not a critique — it's a decision point.

### Review Structure

**Duration:** 30-60 minutes
**Frequency:** Per milestone (kickoff, mid-point, pre-handoff)
**Attendees:** PM, design lead, engineering lead, relevant stakeholders

**Agenda:**

| Phase | Time | Purpose |
|-------|------|---------|
| **Context** | 5 min | What problem are we solving? What did we learn in discovery? |
| **Walkthrough** | 15-25 min | Designer walks through the solution. Explains the rationale, not just the visuals |
| **Questions** | 10-15 min | Stakeholders ask questions. Clarifications, concerns, business considerations |
| **Decision** | 5 min | PM or Decider: approve, approve with changes, or revisit. Clear next steps |

### Review Best Practices

1. **Present the problem first.** Stakeholders who understand the problem give better feedback on the solution
2. **Show the exploration.** "We considered 3 approaches. Here's why we chose this one." Prevents "Did you think about...?"
3. **Show user evidence.** "In 5 user tests, 4 found this intuitive." Evidence is more persuasive than argument
4. **Be specific about what you need.** "I need a go/no-go on this direction" or "I need your input on the pricing display"
5. **Timebox questions.** Stakeholders can ask endlessly. Facilitator manages time
6. **Separate "I don't like it" from "users won't understand it."** The first is a preference. The second is a hypothesis to test

---

## Retrospectives

### Design Team Retro

**Duration:** 45 minutes
**Frequency:** Bi-weekly or end of each sprint
**Attendees:** Design team + optionally PM and eng lead

**Format (Start/Stop/Continue):**

| Column | Prompt |
|--------|--------|
| **Start** | What should we start doing that we're not doing today? |
| **Stop** | What should we stop doing because it's not working? |
| **Continue** | What's working well that we should keep doing? |

**Process:**
1. Silent brainstorm (5 min) — everyone writes stickies
2. Share and cluster (10 min) — read aloud, group similar themes
3. Dot vote (3 min) — each person gets 3 dots
4. Discuss top items (15 min) — focus on the 2-3 highest-voted topics
5. Action items (5 min) — assign owners and deadlines for improvements

### Common Retro Themes and Fixes

| Theme | Typical Action |
|-------|---------------|
| "Designs keep changing after handoff" | Add a design freeze milestone before handoff. All changes after freeze go through change request |
| "Engineers don't follow the spec" | Improve spec quality (more annotations, state coverage). Add design QA to the pipeline |
| "We never have time for design QA" | Block QA time in the sprint. It's not optional — it's part of "done" |
| "Critique doesn't feel safe" | Revisit critique rules. Senior designers model vulnerability by presenting early work first |
| "We're always behind" | Design working 1 sprint ahead. Or reduce scope — doing less, better |
| "No one reads the docs" | Docs are too long or in the wrong place. Move key info into Figma annotations and ticket descriptions |

---

## Ritual Calendar

### Weekly Cadence (Example)

| Day | Time | Ritual |
|-----|------|--------|
| Monday | 10:00 | Sprint planning (whole team) |
| Monday | 14:00 | Design team sync (designers only, 15 min) |
| Tuesday | 10:00 | Design critique (designers + optional guests) |
| Wednesday | 14:00 | Design-eng sync (design lead + eng lead) |
| Thursday | — | Deep work day (no meetings for designers) |
| Friday | 10:00 | Design review (if milestone reached) |
| Friday | 14:00 | Retro (bi-weekly) |

### Sprint-Level Cadence

| Sprint Phase | Design Activity |
|-------------|----------------|
| **Sprint planning** | Confirm designs for this sprint are ready. Flag any gaps |
| **Sprint (week 1)** | Design works on next sprint's features. Answers questions on current sprint |
| **Sprint (week 2)** | Design QA on current sprint's implementation. Handoff for next sprint |
| **Sprint review** | Show what was built. Compare to design spec. Note deviations |
| **Retro** | Review process. Capture improvements |

### Quarterly Cadence

| Timing | Activity |
|--------|---------|
| **Quarter start** | Design planning: align on quarterly goals, major features, research needs |
| **Mid-quarter** | Design ops audit: How are rituals working? What metrics have improved? |
| **Quarter end** | Design debt review: What inconsistencies have accumulated? Prioritize fixes for next quarter |
| **Ongoing** | Design system updates: New components, pattern changes, token updates |

---

## Meeting-Free Time

Protect deep work time. Designers need uninterrupted blocks for creative work.

**Rules:**
1. **One meeting-free day per week minimum** — Thursday is a common choice
2. **No meetings before 10am or after 4pm** — protect morning and late-afternoon focus time
3. **Maximum 2 hours of meetings per day** — anything more cuts into productive design time
4. **Batch meetings** — stack meetings on 2-3 days, keep other days clear
5. **25/50-minute meetings** — end 5-10 minutes early to prevent back-to-back meeting fatigue

**Tracking:** If designers report spending >40% of their time in meetings, the ritual calendar needs trimming. The most common culprits are redundant syncs and reviews that could be async.
