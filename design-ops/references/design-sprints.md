# Design Sprints

Deep reference for planning and facilitating design sprints. Based on Jake Knapp's Sprint methodology from Google Ventures, adapted with practical variations for different team contexts.

---

## Pre-Sprint Preparation

### Choosing the Right Challenge

A good sprint challenge is:
- **Big enough** to matter — solving it would meaningfully move the business or product
- **Urgent enough** to justify 5 days of focused time from 5-7 people
- **Uncertain enough** that the team doesn't already know the answer
- **Testable** within one week — you can build a prototype and get user feedback

**Bad sprint challenges:**
- "Redesign the homepage" — too broad, no specific problem
- "Fix the button color" — too small, doesn't need a sprint
- "Build the Q3 roadmap" — not a design problem

**Good sprint challenges:**
- "New users drop off during onboarding — 68% don't complete setup. Why, and what can we do?"
- "Enterprise customers say our reporting is unusable. Can we find an approach that works before committing engineering?"
- "We're entering a new market segment. What should the first experience look like?"

### Sprint Logistics

| Item | Requirement |
|------|------------|
| **Room** | Dedicated room for the full week. Two whiteboards minimum. No shared spaces |
| **Team size** | 5-7 people. Under 5 lacks diversity of perspective. Over 7 slows everything down |
| **Calendar** | Block 10am-5pm, Monday through Friday. No meetings, no exceptions |
| **Materials** | Whiteboards, markers (thick, multiple colors), sticky notes (3×5), dot stickers, printer paper, tape, timer |
| **Snacks** | High-protein morning snacks, light lunch. No sugar crashes |
| **Devices** | Phones and laptops put away during sessions. Available during breaks only |
| **Prototype tool** | Figma, Keynote, or whatever the team is fastest with — decided before the sprint |
| **Recruiting** | 5 test participants scheduled for Friday, recruited before the sprint starts |

### Recruiting Test Participants

Recruit before the sprint. Friday testing can't slip.

| Method | Lead Time | Best For |
|--------|-----------|----------|
| Existing user database | 3-5 days | Established products with user access |
| Screening survey | 5-7 days | Specific demographic or behavior criteria |
| Recruitment agency | 7-10 days | Hard-to-reach audiences |
| Hallway testing | 0 days | Early-stage, low-fidelity concepts (last resort) |
| UserTesting.com / similar | 1-2 days | Remote testing, fast turnaround |

**Screen for behavior, not demographics.** "Have you searched for a recipe online in the past week?" is better than "Are you aged 25-34?"

Schedule 5 participants at 60-minute intervals: 9am, 10am, 11am, 1pm, 2pm. The team watches together.

---

## Day-by-Day Deep Dive

### Monday: Map

**Goal:** Agree on the problem worth solving and choose a specific target area for the sprint.

**Morning (10am-1pm):**

1. **Set a long-term goal** (20 min)
   - Ask: "Why are we doing this sprint? If everything goes perfectly, what's true in 2 years?"
   - Write the goal on the whiteboard. It stays there all week
   - Example: "Become the go-to tool for small team task management by making setup effortless"

2. **List sprint questions** (20 min)
   - Ask: "What questions do we need to answer this week? What could cause this to fail?"
   - Phrase as "Can we...?" or "Will users...?"
   - Example: "Can we get a team set up in under 5 minutes?" "Will managers adopt a tool their team chose?"

3. **Make a map** (60-90 min)
   - Draw the user journey from left to right on the whiteboard
   - Actors on the left, end goal on the right, key steps in between
   - Keep it simple — 5-15 steps. This is a map, not a flowchart
   - Include the moments where the sprint questions apply

**Afternoon (2pm-5pm):**

4. **Ask the experts** (60-90 min)
   - Bring in 2-4 people who aren't in the sprint but have relevant knowledge: customer support lead, sales, data analyst, subject matter expert
   - Each expert talks for 10-15 minutes. Team asks questions
   - As experts talk, team adds "How Might We" notes on stickies (one idea per sticky)

5. **Organize HMW notes** (20 min)
   - Stick all HMWs on the wall. Silent clustering — group similar themes
   - Dot vote: each person gets 2 dots, Decider gets 4

6. **Pick a target** (15 min)
   - Decider chooses one area of the map to focus on for the rest of the week
   - The target should align with the highest-voted HMWs and sprint questions
   - Announce: "This week, we're solving [target]"

### Tuesday: Sketch

**Goal:** Generate a diverse set of solutions. Individual work, not group brainstorming.

**Morning (10am-1pm):**

1. **Lightning demos** (60 min)
   - Each person presents 2-3 examples of existing products or solutions that inspire them (3 min each)
   - Can be competitors, analogous products, or solutions from unrelated industries
   - Capture the big idea from each demo on the whiteboard

2. **Divide or swarm** (10 min)
   - If the target can be split into parts, assign different parts to different people
   - If not, everyone tackles the same problem from different angles

**Afternoon (2pm-5pm):**

3. **Four-step sketch process** (each person works alone)

   | Step | Time | Activity |
   |------|------|----------|
   | **Notes** | 20 min | Review the whiteboard material. Jot down key ideas |
   | **Ideas** | 20 min | Rough sketches. Quantity over quality. Circles and arrows |
   | **Crazy 8s** | 8 min | Fold paper into 8 panels. One variation per panel. 1 minute each. Forces rapid ideation |
   | **Solution sketch** | 60-90 min | One detailed, three-panel solution sketch. This is the real output. Must be self-explanatory — no verbal presentation |

**Rules for sketching:**
- **No group brainstorming.** Research consistently shows individuals generate more and better ideas when working alone
- **Self-explanatory sketches.** Include titles, annotations, callouts. Someone should understand it without explanation
- **Words matter.** Use real headlines and labels, not "lorem ipsum"
- **Ugly is fine.** Stick figures, boxes, and arrows. The idea matters, not the rendering

### Wednesday: Decide

**Goal:** Choose the best solution without endless debate.

**Morning (10am-1pm):**

1. **Art museum** (15 min)
   - Tape all solution sketches on the wall. Team walks around silently, reading each one

2. **Heat map** (15 min)
   - Each person gets dot stickers (many — 20+). Place dots on parts of sketches they find interesting
   - No discussion. Dots are a signal, not a vote

3. **Speed critique** (45-60 min)
   - For each sketch: facilitator narrates what they see (3 min) → team calls out standout ideas (2 min) → creator clarifies misunderstandings (1 min)
   - Capture big ideas on stickies. Stick them above each sketch

4. **Straw poll** (10 min)
   - Each person gets one supervote sticker. Place it on the solution (or part of a solution) they think should be prototyped
   - This is advisory — the Decider makes the final call

5. **Decider decides** (10 min)
   - The Decider places their supervote(s). That's the direction
   - If two strong solutions conflict: consider a "rumble" — prototype both and test head-to-head

**Afternoon (2pm-5pm):**

6. **Storyboard** (2-3 hours)
   - Draw the test prototype as a storyboard: ~10-15 frames on the whiteboard
   - Start with the "opening scene" — how does the user find this? Google search? Email link? Direct URL?
   - Each frame is one step or screen. Include enough detail for Thursday's prototype team
   - The storyboard IS the prototype spec

### Thursday: Prototype

**Goal:** Build a realistic facade that can fool a user for 60 minutes.

**Principles:**
- **Goldilocks quality** — Real enough to get honest reactions, fake enough to build in one day
- **Facade, not product** — It looks real but nothing works behind the scenes
- **Focus on the test flow** — Only build what the user will interact with during Friday's test

**Team roles:**

| Role | Who | Does What |
|------|-----|----------|
| **Makers** | 2-3 people (usually designers) | Build the prototype screens/pages |
| **Stitcher** | 1 person | Connects screens into a clickable flow. Ensures consistency |
| **Writer** | 1 person | Writes all copy. Real headlines, real button labels, real error messages |
| **Asset collector** | 1 person | Finds placeholder photos, icons, data. Nothing generic |
| **Interviewer** | 1 person | Writes the interview script and test plan for Friday |

**Prototype tool selection:**

| Tool | Best For | Speed |
|------|----------|-------|
| **Figma** | Digital products (web, mobile) | Fast if team knows it |
| **Keynote/PowerPoint** | Click-through flows, presentations | Very fast |
| **HTML/CSS** | Interactive prototypes, animations | Slower but more realistic |
| **Paper** | Physical products, early concepts | Fastest |
| **Video** | Service experiences, multi-touchpoint flows | Medium |

**End of day:** Full run-through of the prototype. Everyone watches. Fix anything that breaks the illusion.

### Friday: Test

**Goal:** Watch 5 real users interact with the prototype. Identify patterns.

**Schedule:**

| Time | Activity |
|------|----------|
| 9:00-10:00 | User 1 interview |
| 10:00-10:15 | Debrief + notes |
| 10:15-11:15 | User 2 interview |
| 11:15-11:30 | Debrief + notes |
| 11:30-12:30 | User 3 interview |
| 12:30-1:30 | Lunch + mid-point check |
| 1:30-2:30 | User 4 interview |
| 2:30-2:45 | Debrief + notes |
| 2:45-3:45 | User 5 interview |
| 3:45-5:00 | Final debrief + decision |

**Interview structure (60 min per user):**

1. **Warm-up** (5 min) — Build rapport. Ask about their background and context
2. **Context questions** (10 min) — How they currently handle the problem the sprint is solving
3. **Prototype walkthrough** (35 min) — "Think out loud as you go." Minimal guidance from interviewer
4. **Debrief** (10 min) — Overall impressions, comparisons, final questions

**Observation setup:**
- Interviewer is alone with participant (in person or video call)
- Rest of the team watches from a separate room via screen share
- Each observer has a note grid: rows = interview sections, columns = participants
- Use stickies: green = positive reaction, red = negative, yellow = neutral/interesting

**Identifying patterns (final debrief):**

| Pattern Type | Threshold | Action |
|-------------|-----------|--------|
| **5/5 users** had the same reaction | Strong signal | Act on it with high confidence |
| **3-4/5 users** had the same reaction | Good signal | Act on it, but watch for edge cases |
| **2/5 users** had the same reaction | Weak signal | Note it, but don't pivot on this alone |
| **1/5 users** had a unique reaction | Noise or outlier | Ignore unless it reveals a new insight |

---

## Sprint Variations

### Mini Sprint (3 Days)

For smaller problems or when you can't block a full week:

| Day | Covers | Original Days |
|-----|--------|---------------|
| Day 1 | Map + Sketch | Monday + Tuesday |
| Day 2 | Decide + Prototype | Wednesday + Thursday |
| Day 3 | Test | Friday |

**Trade-offs:** Less divergent thinking, simpler prototype, same quality of testing.

### Remote Sprint

| Challenge | Adaptation |
|-----------|-----------|
| Whiteboard | Miro, FigJam, or similar — one board per day |
| Sketching | Paper sketches → photo and upload. Or digital sketching tools |
| Dot voting | Built-in voting features in Miro/FigJam |
| Energy management | Shorter sessions (max 90 min), more breaks, cameras on |
| Time zones | Overlap of at least 4 hours required. Async prep work helps |
| Prototyping | Figma works well remotely. Assign roles via Slack/chat |
| Testing | Remote testing via Zoom. Observer room is a separate Zoom call |

### Design Sprint for Existing Products

When the product already exists, adapt the sprint:

- **Monday mapping** uses real analytics data, not assumptions — show the funnel, the drop-offs, the support tickets
- **Lightning demos** include the current product as one of the examples — what's working and what isn't
- **Prototype** can be a modified version of the real product, not a from-scratch build
- **Friday testing** compares the new approach against the existing experience (A/B within the test session)

---

## Post-Sprint Actions

The sprint ends Friday, but the work continues:

| Timeframe | Action |
|-----------|--------|
| **Friday afternoon** | Decider announces go/no-go/pivot. Document the decision and reasoning |
| **Monday after** | Share sprint results with broader team. Distribute the test video highlights |
| **Week after** | If go: break the solution into stories, estimate, schedule. If no-go: document what was learned, decide next step |
| **2 weeks after** | Sprint retro — what worked about the sprint process itself? |
| **Ongoing** | Reference sprint artifacts when making related decisions — the map, the sketches, the test results |

### Sprint Artifacts to Preserve

| Artifact | Format | Purpose |
|----------|--------|---------|
| Sprint map | Photo of whiteboard → stored in project docs | Problem context for anyone joining later |
| Sprint questions | Text document | Track which questions were answered, which remain |
| Solution sketches | Photos → stored in project docs | Record of ideas explored (including rejected ones) |
| Storyboard | Photo of whiteboard | The chosen direction, in detail |
| Prototype | Figma file / Keynote | Reference for implementation |
| Test recordings | Video files (with consent) | Evidence for stakeholders, onboarding new team members |
| Pattern summary | Written document | Key findings: what worked, what failed, what surprised |
| Decision log | Written document | What was decided and why — prevents relitigating |
