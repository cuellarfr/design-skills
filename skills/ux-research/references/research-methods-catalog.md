# Research Methods Catalog

Detailed guide to UX research methods organized by type. Each method includes when to use it, what it reveals, practical steps, and tips.

## Looking Methods
> Methods for observing human experience

### Interviewing
> Gathering information through direct dialogue

**Best for:** Generative research, understanding goals, motivations, mental models
**Participants:** 5-8 per segment
**Time:** 45-60 minutes per session

**Benefits:**
- Gain information directly from users
- Challenge your preconceptions
- Deepen empathy
- Build credibility with stakeholders

**Process:**
1. Identify a topic for investigation
2. Prepare your questions and recording equipment
3. Determine criteria for selecting interviewees
4. Identify and recruit participants
5. Set a time and place to meet
6. Introduce yourself and the purpose; obtain consent
7. Start with easy questions, then draw out specifics
8. Listen carefully and take good notes
9. Thank each participant

**Tips:**
- Choose a location with minimal distractions
- Don't put words into the interviewee's mouth
- Resist the urge to analyze during the session
- Note exact vocabulary participants use

See `references/interviewing-guide.md` for the complete technique.

---

### Fly-on-the-Wall Observation
> Observing people in an unobtrusive manner

**Best for:** Understanding natural behavior, identifying workarounds, discovering unarticulated needs
**Participants:** Observe 5-10 people/sessions
**Time:** 2-4 hours per observation session

**Benefits:**
- Diminishes your presence as a researcher
- Reveals behavior people don't report in interviews
- Challenges assumptions about how people work
- Informs subsequent research activities

**Process:**
1. Identify a subject area to study
2. Develop a plan to guide your investigation
3. Consider which people and activities to watch
4. Choose a location to visit
5. Obtain necessary access and permissions
6. Prepare materials for capturing what you see
7. Go out and observe
8. Record findings in videos, photos, and notes

**Tips:**
- Make every effort to blend into the background
- Take on the role of an objective bystander
- Look at the situation from several vantage points
- Don't interact unless necessary

---

### Contextual Inquiry
> Interviewing and observing people in their own environment

**Best for:** Understanding real workflows, environment factors, workarounds, tool usage
**Participants:** 4-8 participants
**Time:** 1-2 hours per session (plus travel)

**Benefits:**
- Reveals what people actually do vs. what they say they do
- Captures environmental factors that affect product use
- Surfaces workarounds and pain points invisible in lab settings
- Produces accurate scenarios for design

**Process:**
1. Identify a location and people to be involved
2. Prepare questions and recording equipment
3. Go to the site
4. Introduce yourself and the purpose; obtain consent
5. Ask participants to do tasks in their normal way
6. Observe their actions unobtrusively
7. Interject questions at opportune moments
8. Record findings in videos, photos, and notes
9. Thank each participant

**Things to keep in mind:**
- Plan for travel time
- Get situated without interrupting routines
- Establish trust, don't be disruptive
- Note everything in as much detail as possible
- Summarize immediately after

**Tips:**
- Ask people to do activities, not just give you a tour
- Use more than one researcher for multiple perspectives
- Stay focused on your goals, yet open to discovery

---

### Walk-a-Mile Immersion
> Building empathy through firsthand experience

**Best for:** Deeply understanding user frustrations, physical and emotional experiences
**Participants:** The researcher themselves
**Time:** Varies (hours to days)

**Process:**
1. Identify whose experience you want to replicate
2. Choose the tasks and activities to perform
3. Assemble what's needed for a realistic simulation
4. Determine the best location
5. Obtain necessary access and permissions
6. Conduct the targeted tasks as realistically as possible
7. Note findings along the way

**Tips:**
- Commit fully — don't give up early
- Ask another observer to help capture findings
- Consider accessibility simulation tools to understand impaired experiences

---

## Participatory Methods
> Learning from people through cooperative design activities

### What's on Your Radar?
> People plot items according to personal significance

**Best for:** Understanding priorities, revealing what people care about most
**Participants:** 5-10 stakeholders or users
**Time:** 30-45 minutes

**Process:**
1. Identify a topic for consideration
2. Make a large poster that looks like a radar screen (3 concentric circles, 4-6 segments)
3. Label circles: Primary, Secondary, Tertiary
4. Label segments as subcategories of the topic
5. Give each person a poster, pen, and sticky notes
6. Instruct them to plot their personal considerations
7. Ask participants to describe their rankings

**Tips:**
- Limit plotting time to 15 minutes
- Allow participants to write in some segment labels
- Listen closely when people describe their choices

---

### Buy a Feature
> A game using artificial money to express trade-off decisions

**Best for:** Understanding feature priorities, revealing what users truly value
**Participants:** 4-8 stakeholders or users
**Time:** 45-60 minutes

**Process:**
1. Identify a product or service to focus on
2. Generate a list of potential features
3. Make playing cards for each feature with a price tag
4. Give each player a limited amount of artificial money
5. Ask them to purchase features within their budget
6. Encourage them to articulate their deliberations

**Tips:**
- Pricing can be based on actual cost of execution
- Listen for evidence of motivations and priorities
- Have participants make buying decisions in pairs for richer discussion

---

### Card Sorting
> Understanding how users categorize and organize information

**Best for:** Information architecture, navigation structure, labeling
**Time:** 30-45 minutes per session

**Types:**

| Type | What Participants Do | What You Learn | When to Use |
|---|---|---|---|
| **Open sort** | Create their own groups and name them | How users naturally categorize; what labels they use | Early exploration, new IA, understanding mental models |
| **Closed sort** | Sort cards into your predefined categories | Whether your categories work for users | Validating a draft IA, adding content to existing structure |
| **Hybrid** | Sort into predefined categories but can create new ones | Whether your categories cover the space | Refining an IA that's partially validated |

**Important:** A closed sort tests *classification*, not *findability*. If users can sort "Account settings" into "Profile," it doesn't mean they'll navigate there. Use tree testing or task-based testing to validate findability.

**Participants:**
- **Exploratory analysis (patterns and themes):** 8-10 participants is often sufficient
- **Statistical analysis (dendrograms, clusters):** 15-30+ for meaningful statistical patterns
- **Team sorts (collaborative, generative):** 3-5 groups of 2-3 people — good for hearing reasoning, not for statistics

#### Choosing Content

Poorly chosen content is the most common reason card sorts fail.

| Principle | Right | Wrong |
|---|---|---|
| **Consistent granularity** | All items are page-level topics | Mix of "Homepage," "FAQ," and "Shipping returns policy for international orders" |
| **Representative range** | Content spans the full breadth of the site/product | Only items from one section, skewing the groupings |
| **Neutral framing** | Items don't suggest their own category | "Marketing resources" → participants just create a "Marketing" group |
| **Right quantity** | 30-60 cards for individual sorts; 20-40 for team sorts | 100+ cards cause fatigue; fewer than 20 lack enough variety |

**Content sources:**
- New product → wish list of content types and features
- Existing product → content inventory or audit (sample representative items, don't include everything)
- Application → tasks, functions, and menu items

#### Running the Sort

**Facilitation tips:**
- Do a test run first — catches duplicate content, confusing titles, and bad instructions
- Let participants work at their own pace
- Anticipate questions: "Can I put a card in two groups?" (usually yes for physical; depends on tool for digital)
- For team sorts: listen to the *discussion*, not just the final grouping — reasoning is as valuable as results
- For open sorts: ask participants to name their groups *after* sorting, not before (naming first biases the grouping)
- Take notes on body language, hesitation, and verbal reasoning

**Physical vs. digital:**
- **Physical cards** (3"×5" index cards) — Better for face-to-face sorts, richer observation, team discussions
- **Online tools** (OptimalSort, UserZoom, etc.) — Better for remote participants, larger samples, automatic data capture

#### Analysis: Two Approaches

Always do exploratory analysis first. Statistical analysis is optional and requires 15+ participants.

**Exploratory analysis** (do this every time):

1. **Look at each participant's results individually** — What classification schemes did they use? (Topic, task, audience, format?)
2. **Create a spreadsheet** — Cards as rows, participant groups as columns. Look for where cards consistently land together
3. **Identify strong pairs** — Which cards always go together across participants? These are natural siblings
4. **Identify scattered cards** — Which cards end up in different groups for different people? These are ambiguous items that may need their own category or clearer labeling
5. **Examine group labels** — What words did participants use? These are candidates for your navigation labels
6. **Note outlier reasoning** — Sometimes one participant's unusual grouping reveals an insight everyone else missed

**Statistical analysis** (for 15+ participants):

| Method | What It Shows | How to Read It |
|---|---|---|
| **Similarity matrix** | How frequently each pair of cards was grouped together (percentage) | 70%+ = strong association → these belong together. 30-70% = moderate → investigate. Below 30% = weak → probably different categories |
| **Hierarchical cluster analysis (dendrogram)** | Tree diagram showing which cards cluster together and at what level of similarity | Read bottom-up: cards that merge at lower levels are more closely related. Cut the tree at different heights to see different numbers of groups |
| **Multidimensional scaling (MDS)** | 2D plot showing spatial "distance" between cards based on how often they were co-sorted | Cards close together were frequently grouped together. Clusters on the plot suggest natural categories. Isolated cards are ambiguous |

**Cautions with statistics:**
- Don't rely on statistics alone — they can suggest a tidy answer that doesn't reflect the messiness of real data
- Always combine with exploratory analysis to understand *why* patterns exist
- Statistical methods work poorly with fewer than 15 participants

#### Applying Results to Information Architecture

Card sort results are one input, not a dictation. Combine with business requirements, content strategy, and technical constraints.

| Finding | IA Action |
|---|---|
| Strong card clusters with consistent labels | These are your primary categories — use participant labels as starting points |
| Cards that land in different groups for different people | Consider cross-linking, faceted access, or multiple navigation paths |
| Participant labels that differ from your current labels | Test the participant labels — they may work better because they match user language |
| Groups that are too large (15+ cards) | Split into subcategories; use participant reasoning to find natural divisions |
| Groups that are too small (1-2 cards) | Merge with a related group, or reconsider whether these items need their own category |
| Multiple classification schemes across participants | Consider providing multiple navigation approaches (by topic, by task, by audience) |

**After the card sort:** Validate the resulting IA with a tree test — give users tasks and ask them to navigate the category structure to find the right answer. Card sorting tells you how to organize; tree testing tells you if people can find things.

---

### Build Your Own
> People express ideal solutions using symbolic elements

**Best for:** Uncovering latent needs, discovering what users actually want
**Participants:** 4-8 in pairs
**Time:** 30-60 minutes

**Process:**
1. Identify a product or service to focus on
2. Make a kit of representational building blocks (shapes, symbols)
3. Divide group into teams of two
4. Give each team a construction kit
5. Ask them to build an expression of an ideal solution
6. Encourage "thinking aloud" as they construct
7. Ask each team to present their final model

---

### Journaling / Diary Studies
> People record personal experiences over time

**Best for:** Understanding experiences over time, capturing in-the-moment reactions, remote research
**Participants:** 8-15 participants
**Time:** 1-4 weeks

**Process:**
1. Define the experience or behavior to track
2. Create a structured journal template (digital or physical)
3. Brief participants on what to record and when
4. Send regular reminders (but don't over-prompt)
5. Collect journals at the end of the study period
6. Analyze entries for patterns across participants and time

---

## Evaluative Methods
> Testing designs and solutions

### Usability Testing
> Observing representative users attempting tasks with a design

**Best for:** Identifying interaction problems, validating design decisions
**Participants:** 3-5 per round
**Time:** 30-60 minutes per session

See `references/usability-testing-guide.md` for the complete process, scoring rubrics, and triage framework.

**What usability testing CAN do:**
- Uncover problems with labeling, structure, mental model, and flow
- Reveal whether interface language works for your audience
- Show how users think about the problems you're solving
- Demonstrate to stakeholders whether the approach meets goals

**What usability testing CANNOT do:**
- Provide a story, vision, or breakthrough design
- Tell you whether the product will succeed in the market
- Tell you which user tasks are more important than others
- Substitute for QA testing

**Usability has 5 quality components:**
- **Learnability:** How easy for first-time users to accomplish basic tasks?
- **Efficiency:** Once learned, how quickly can users perform tasks?
- **Memorability:** After time away, how easily can users reestablish proficiency?
- **Errors:** How many, how severe, and how easily recovered?
- **Satisfaction:** How pleasant to use?

---

### Heuristic Evaluation
> Expert review against established usability principles

**Best for:** Quick identification of obvious usability issues before user testing
**Evaluators:** 2-3 minimum (each finds different issues)
**Time:** 1-2 hours per evaluator

**Nielsen's 10 Heuristics:**
1. **System status visibility:** Appropriate feedback within 400ms
2. **Match with real world:** Language and conventions familiar to users
3. **User control and freedom:** Emergency exits, undo, redo
4. **Consistency and standards:** Same things behave the same way
5. **Error prevention:** Help users avoid errors, not just recover
6. **Recognition over recall:** Options visible, instructions findable
7. **Flexibility and efficiency:** Shortcuts for expert users
8. **Aesthetic and minimalist design:** No irrelevant information
9. **Help users recover from errors:** Error messages that help
10. **Help and documentation:** Task-oriented, easy to find

**Severity Rating Scale (0-4):**
- **0 — Not a problem:** Cosmetic only
- **1 — Cosmetic:** Fix if time permits
- **2 — Minor:** Low priority
- **3 — Major:** High priority, causes significant difficulty
- **4 — Catastrophic:** Must fix before release

**Pros:** Quick, cheap, catches basic issues early
**Cons:** Simplistic, won't catch all issues — not a substitute for usability testing

---

### Tree Testing
> Evaluating findability within a site's hierarchy

**Best for:** Validating information architecture without visual design influence
**Participants:** 20-50 for quantitative results
**Time:** 15-20 minutes per participant

**Process:**
1. Create a text-only representation of your site hierarchy
2. Write task scenarios ("Where would you find X?")
3. Participants navigate the tree to find where they'd expect each item
4. Measure success rate, directness (first click accuracy), and time to complete

---

### A/B Testing
> Comparing two versions to determine which performs better

**Best for:** Validating specific design decisions with statistical confidence
**Participants:** Depends on traffic (need 95% confidence level)
**Time:** Run until statistical significance is reached

**Process:**
1. Select your goal metric
2. Create variations (change one thing at a time)
3. Choose an appropriate start date
4. Run until 95% confidence level
5. Review the data
6. Decide: stick with control, switch to variation, or run more tests

**Caution:** A/B testing can be seductive because it promises mathematical certitude. But human decision-making is still necessary. The best response to a UI question is not always a test.

---

## Synthesis Methods
> Turning data into insights and models

### Affinity Diagramming
> Grouping observations into themes

See `references/analysis-synthesis.md` for the complete process.

### Empathy Mapping
> Articulating what you know about a user type

**Four quadrants:**
1. **What the user says** — Direct quotes and statements
2. **What the user does** — Actions and behaviors observed
3. **What the user thinks** — Thoughts, beliefs, concerns (may not be explicit)
4. **What the user feels** — Emotional state throughout the experience

### Journey Mapping
> Visualizing the user flow from a high-level perspective

**For each step, document:**
- **Goal** — What is the user trying to accomplish?
- **Actions** — What does the user do?
- **Touchpoint** — What parts of the product are involved?
- **Thinking** — What is the user thinking?
- **Feeling** — What is the user feeling?
- **Opportunities** — How can we improve this step?
- **Ownership** — Who on the team is responsible?

### Persona Creation
> Composite user archetypes from research data

See `references/analysis-synthesis.md` for the complete persona creation process.
