# Usability Testing Guide

A complete guide to planning, conducting, and analyzing usability tests. Combines established usability testing frameworks and methodologies.

## When to Use Usability Testing

Test early. Test often. Never right before lunch.

- Before designing: test comparable or competitor sites
- During design: test wireframes and prototypes
- Before launch: test the near-final product
- After launch: test to identify improvement opportunities

**Two kinds of testing:**
- **"Get it" testing:** Show users the site/product. Do they understand the purpose, value proposition, organization, and how it works?
- **Key task testing:** Ask users to complete specific tasks. Watch how well they do.

## Planning a Test

### Decide What to Test

**Good test candidates:**
- Core user flows (onboarding, checkout, search)
- New features or redesigned areas
- Areas where analytics show drop-off or confusion
- Competitor products (for benchmarking)
- Multiple design concepts (comparative testing)

### Write a Test Plan

Use `templates/usability-test-plan-template.md` for the full template.

**Essential elements:**
- Objectives (what questions will this test answer?)
- Subject of the test (prototype, live product, competitor)
- Methodology (moderated/unmoderated, remote/in-person)
- Participants (number, criteria, recruiting method)
- Task scenarios (4-6 per session)
- Usability goals (completion rate, error-free rate, time on task)
- Success metrics (what constitutes "pass" for each task?)

### Write Task Scenarios

Tasks should be:
- **Scenario-based:** Give context, not just instructions
- **Goal-oriented:** Focus on what the user wants to achieve, not the steps
- **Realistic:** Based on actual use cases from personas or analytics
- **Neutral:** Don't use the same words that appear in the interface

**Example — Bad:**
> "Click on the Account Settings menu and change your email address."

**Example — Good:**
> "You recently changed your email address. Show me how you'd update it in this app."

**Example — Bad:**
> "Use the search filter to find running shoes under $100."

**Example — Good:**
> "You're looking for a pair of running shoes and your budget is under $100. Find a pair you'd consider buying."

### How Many Users?

**Per round: 3-5 users**

- 3 users catches the most obvious problems and allows same-day debrief
- 5 users catches approximately 85% of usability issues
- More users in a single round has diminishing returns
- Better to do 3 rounds of 3 than 1 round of 9

**Why small and frequent beats large and rare:**
- Faster feedback loops
- Less pressure to "get it right" in one test
- Each round can test fixes from the previous round
- Lower cost per round = more rounds = better product

### How Many Tasks?

- **30-minute session:** 3-4 tasks
- **60-minute session:** 5-7 tasks
- Order tasks from easy to difficult
- Include at least one "Get It" task at the beginning
- Save the most important task for when the participant is warmed up (task 2 or 3)

## Recruiting

**Key principle:** The importance of recruiting perfectly representative users is overrated. Testing early and often with imperfect participants is far better than waiting for perfect ones.

**Good enough participants:**
- Share key goals with target users
- Have similar tech proficiency
- Are NOT employees or close friends of the team (for formal rounds)
- Can articulate their thoughts while working

**Recruiting tips:**
- Offer reasonable incentives ($50-100/hour consumer, more for B2B)
- Keep the invitation simple
- Don't discuss the product beforehand
- For early/informal rounds: friends, neighbors, and hallway testing are fine
- Maintain an ongoing database of potential participants

Use `templates/screener-template.md` to write a screening survey.

## Running the Test

### Roles

- **Facilitator:** Guides the participant through tasks. Should NOT be the designer or developer — they can't sit idly while their creation fails.
- **Observer/Notetaker:** Takes structured notes while watching. Records task outcomes, timestamps, and quotes.
- **Team observers:** Watch from a separate room or screen. Everyone on the team should be encouraged to attend.

### Setup

**In-person:**
- Quiet room with two chairs, computer, and recording equipment
- Video cable to a TV in another room for team observation
- Screen recording software (with audio)
- Water for the participant

**Remote:**
- Video conferencing with screen sharing
- Ask participant to share their screen and think aloud
- Record the session (with permission)
- Have a backup plan if tech fails

### Facilitation Script

**Opening (5 min):**
> "Thanks for coming. I'm going to ask you to try some things on [product] and tell me what you think as you go. This isn't a test of you — we're testing the product. There are no wrong answers. If you get stuck, that's valuable information for us. I may not be able to help you during the tasks because I want to see what a real user would experience. Please think out loud — tell me what you're looking at, what you're trying to do, and what you're thinking."

**Before each task:**
> "I'm going to read you a scenario. Take a moment to read it on this card, then show me how you'd approach it."

**During tasks:**
- Stay quiet unless the participant is completely stuck or silent
- If silent: "What are you thinking right now?"
- If stuck for 2+ minutes: "What would you do if I weren't here?"
- If completely blocked: note the failure and move to the next task
- Never say "click there" or "try the menu" — let them struggle

**Probing questions (after each task):**
- "What did you expect to happen when you clicked that?"
- "Was anything confusing or unexpected?"
- "On a scale of 1-5, how easy was that? Why?"
- "What would you have done if you were at home?"

**Closing (5 min):**
> "That's all the tasks. Before we finish — what was the hardest part? Is there anything else you noticed that you'd like to share?"

### What the Observer Should Capture

For each task, record:
- **Task outcome:** Success / Failure / Partial success
- **Time to complete** (if measuring)
- **Path taken:** What did they click/tap?
- **Errors:** Wrong turns, misclicks, confusion points
- **Verbal reactions:** Direct quotes, especially frustration or confusion
- **Body language:** Sighing, leaning in, squinting (in-person)
- **Assist needed:** Did the facilitator have to intervene?

## Analyzing Results

### Same-Day Debrief (Critical)

After testing 3-4 users, debrief immediately — over lunch is ideal.

**Debrief structure:**
1. Each observer shares their top 3 observations
2. Identify issues that multiple users encountered
3. Rate each issue on severity and frequency
4. Identify quick wins (obvious fixes, low effort)
5. Decide what to fix before the next round

### Severity Scale

| Rating | Label | Definition | Example |
|---|---|---|---|
| **Critical** | Showstopper | Prevents task completion entirely | User cannot find the checkout button |
| **High** | Major | Causes significant difficulty; some users abandon | User repeatedly enters wrong field first |
| **Moderate** | Minor | Causes some difficulty but task is completable | User hesitates at a label but figures it out |
| **Low** | Cosmetic | Noticed but doesn't affect task completion | User comments that a color seems off |

### Frequency Scale

| Rating | Definition |
|---|---|
| **High** | 30%+ of participants experienced the problem |
| **Moderate** | 11-29% of participants experienced the problem |
| **Low** | 10% or fewer participants experienced the problem |

### Issue Triage (3 Tiers)

| Tier | Criteria | Action |
|---|---|---|
| **Tier 1** | High severity + high frequency | Fix immediately — high risk to product success |
| **Tier 2** | Moderate severity/low frequency OR low severity/moderate frequency | Plan for next sprint/cycle |
| **Tier 3** | Low severity + low frequency | Add to backlog |

### Typical Problem Categories

**Users are unclear on the concept:**
They don't get it. They either don't know what to make of the page, or they think they do but they're wrong.
→ Revisit the value proposition, labeling, and overall page purpose.

**The words they're looking for aren't there:**
Either (a) your categories don't match their mental model, or (b) categories are right but labels are wrong.
→ Consider card sorting to realign navigation and labeling.

**There's too much going on:**
What they need is on the page, but they can't see it. Visual noise is hiding it.
→ Reduce noise, improve visual hierarchy, make key elements "pop."

### Triage Guidelines

- **Ignore "kayak" problems:** Users go astray briefly but recover immediately without help. These are normal navigation behavior, not bugs.
- **Resist the impulse to add things:** When users don't get something, the instinct is to add explanations. Often the fix is to remove something that's obscuring the meaning.
- **Be skeptical of feature requests:** "I'd like it if it could do X" — probe deeper. They often have a fine source for X already.
- **Grab the low-hanging fruit:** Focus on "head slappers" (obvious to everyone once seen) and "cheap hits" (minimal effort, high visibility).

## Presenting Findings

Use `templates/findings-report-template.md` for the full report template.

**Key sections:**
1. Executive summary (3-5 bullet points)
2. Methodology (who, what, how)
3. Task results table (task, success rate, average time, key issues)
4. Prioritized findings with severity ratings
5. Recommendations with effort estimates
6. Video clips or screenshots of key moments (most persuasive artifact)

**Persuasion tip:** A 2-minute video clip of a user struggling with a task is worth more than a 20-page report. Always capture highlight clips.

## Benchmarks and Metrics

### Task-Level Metrics
- **Completion rate:** % of users who successfully completed the task
- **Error-free rate:** % of users who completed without any errors
- **Time on task:** Average time to complete (compare across rounds)
- **Single Ease Question (SEQ):** "How easy was this task?" (1-7 scale, asked after each task)
  - Average SEQ across studies: 5.5
  - Below 5.0 indicates a usability problem worth investigating

### Study-Level Metrics
- **System Usability Scale (SUS):** See detailed section below
- **Net Promoter Score (NPS):** "How likely are you to recommend?" (0-10)
  - Promoters (9-10), Passives (7-8), Detractors (0-6)
  - NPS = % Promoters − % Detractors
- **UMUX-Lite:** 2-question alternative to SUS (see below)

### Industry Benchmarks
- Average task completion rate: 78%
- Average SUS score: 68
- Average SEQ score: 5.5
- Target for good usability: 80%+ completion, 75+ SUS, 5.5+ SEQ

---

## System Usability Scale (SUS)

The most widely used standardized usability questionnaire. Developed in 1986, validated across thousands of studies. Takes 1-2 minutes to administer. Requires only 12-14 users for reliable results, but can be used with as few as 5.

### When to Administer

- **After** the participant completes all tasks in a usability test
- **Before** the debrief/interview (capture immediate impression, not post-discussion rationalization)
- Can also be used for periodic benchmarking of a live product (survey existing users)

### The 10 Questions

Participants rate each statement on a 5-point scale: **Strongly Disagree (1)** to **Strongly Agree (5)**.

| # | Statement | Tone |
|---|---|---|
| 1 | I think that I would like to use this system frequently | Positive |
| 2 | I found the system unnecessarily complex | Negative |
| 3 | I thought the system was easy to use | Positive |
| 4 | I think that I would need the support of a technical person to be able to use this system | Negative |
| 5 | I found the various functions in this system were well integrated | Positive |
| 6 | I thought there was too much inconsistency in this system | Negative |
| 7 | I would imagine that most people would learn to use this system very quickly | Positive |
| 8 | I found the system very cumbersome to use | Negative |
| 9 | I felt very confident using the system | Positive |
| 10 | I needed to learn a lot of things before I could get going with this system | Negative |

**Important:** Present all 10 questions together on one page. Don't skip questions or change the wording — the scale is validated as a complete set. The alternating positive/negative tone is intentional (prevents response bias).

### Scoring Formula

SUS scoring is not intuitive — don't just average the raw responses.

**Step 1: Calculate item scores**
- For **odd-numbered items** (positive statements): item score = raw score − 1
- For **even-numbered items** (negative statements): item score = 5 − raw score

This converts all items to a 0-4 scale where higher = better.

**Step 2: Sum and multiply**
- Add all 10 item scores (range: 0-40)
- Multiply by **2.5** to get the SUS score (range: 0-100)

**Example calculation:**

| Question | Raw Score | Calculation | Item Score |
|---|---|---|---|
| Q1 (odd) | 4 | 4 − 1 | 3 |
| Q2 (even) | 2 | 5 − 2 | 3 |
| Q3 (odd) | 5 | 5 − 1 | 4 |
| Q4 (even) | 1 | 5 − 1 | 4 |
| Q5 (odd) | 4 | 4 − 1 | 3 |
| Q6 (even) | 2 | 5 − 2 | 3 |
| Q7 (odd) | 5 | 5 − 1 | 4 |
| Q8 (even) | 1 | 5 − 1 | 4 |
| Q9 (odd) | 4 | 4 − 1 | 3 |
| Q10 (even) | 1 | 5 − 1 | 4 |
| | | **Sum:** | **35** |

SUS Score = 35 × 2.5 = **87.5**

### Interpreting SUS Scores

SUS produces a single number from 0-100, but it's **not a percentage**. Use these interpretation scales:

#### Grade Scale

| SUS Score | Grade | Percentile | Interpretation |
|---|---|---|---|
| 84.1 – 100 | A+ | 96-100 | Users love it. Among the best scores. |
| 80.8 – 84.0 | A | 90-95 | Excellent usability |
| 78.9 – 80.7 | A− | 85-89 | Very good |
| 77.2 – 78.8 | B+ | 80-84 | Good — above average |
| 74.1 – 77.1 | B | 70-79 | Above average |
| 72.6 – 74.0 | B− | 65-69 | Slightly above average |
| 71.1 – 72.5 | C+ | 60-64 | Average |
| 65.0 – 71.0 | C | 41-59 | Average — room for improvement |
| 62.7 – 64.9 | C− | 35-40 | Below average |
| 51.7 – 62.6 | D | 15-34 | Poor — significant usability issues |
| 0 – 51.6 | F | 0-14 | Failing — fundamental usability problems |

#### Adjective Scale

| SUS Score Range | Adjective Rating |
|---|---|
| 85+ | Excellent |
| 73 – 85 | Good |
| 52 – 73 | OK |
| 39 – 52 | Poor |
| Below 39 | Awful |

#### Acceptability Ranges

| SUS Score | Acceptability |
|---|---|
| Above 70 | Acceptable |
| 50 – 70 | Marginal (high end may be OK, low end is problematic) |
| Below 50 | Not acceptable |

### Key Benchmarks

- **Average SUS score across all products:** 68 (this is a C grade, not "good")
- **Target for "good" usability:** 75+ (B grade, 70th percentile)
- **Target for "excellent" usability:** 85+ (A+ grade)
- **A score of 68 is average**, not passing — many teams mistake this for "good enough"

### SUS Subscales

SUS can be split into two factors (though the overall score is most reliable):

| Subscale | Questions | What It Measures |
|---|---|---|
| **Usability** (learnability) | Q4, Q10 | How easy is it to learn? |
| **Usability** (general) | Q1, Q2, Q3, Q5, Q6, Q7, Q8, Q9 | Overall perceived usability |

If the learnability subscale is significantly lower than general usability, the product is usable once learned but has an onboarding problem. If general usability is low but learnability is fine, the product is easy to pick up but frustrating to use.

### Common Mistakes with SUS

| Mistake | Why It's Wrong | Fix |
|---|---|---|
| Treating SUS as a percentage | 68 is average, not "68% usable" | Use grade/percentile tables above |
| Changing the wording | Scale is validated as-is; changes invalidate comparisons | Use exact wording |
| Skipping questions | All 10 are needed for a valid score | If one is missed, impute the average of remaining items with same tone |
| Too few respondents | Individual scores are noisy | Use 12-14+ for reliable averages; 5 minimum for directional signal |
| Only measuring once | A single score has no context | Compare across versions, competitors, or time periods |
| Administering during tasks | Should come after all tasks are complete | Always administer at the end, before debrief |

### Tracking SUS Over Time

SUS is most valuable as a **comparative** measure:

| Comparison | What It Tells You |
|---|---|
| Before vs. after redesign | Did usability actually improve? |
| Your product vs. competitor | Where do you stand in the market? |
| Version N vs. Version N+1 | Are iterative changes moving the needle? |
| Feature A vs. Feature B | Which area of the product needs more work? |

A change of **3+ points** is generally considered meaningful. A change of **10+ points** represents a major shift in perceived usability.

---

## Alternative Usability Questionnaires

SUS isn't always the right tool. Choose based on your constraints:

### UMUX-Lite (2 questions)

Use when you need a **very quick** satisfaction measure — in-app surveys, post-task popups, or when respondent time is extremely limited.

**Questions** (7-point scale, Strongly Disagree to Strongly Agree):
1. "[System name]'s capabilities meet my requirements."
2. "[System name] is easy to use."

**Scoring:** Average the two scores. Can be converted to a SUS-equivalent: `(mean − 1) × (100/6)`.

**Tradeoff:** Much shorter, but less diagnostic. Tells you "there's a problem" but not where.

### Single Ease Question (SEQ)

Use **after each individual task** (not at study level) to measure perceived task difficulty.

**Question:** "Overall, how easy or difficult was this task?" (1 = Very Difficult, 7 = Very Easy)

**Benchmark:** Average across studies is 5.5. Below 5.0 signals a task-level usability issue.

**Best paired with:** Task completion rate. A task with high completion but low SEQ means users succeeded but found it frustrating.

### NASA-TLX (Task Load Index)

Use when you need to measure **cognitive workload** — common in complex/professional tools, safety-critical systems, or comparing two interface approaches for the same task.

**6 subscales:** Mental demand, Physical demand, Temporal demand, Performance, Effort, Frustration (each rated 0-100).

**When to use over SUS:** When "how usable" matters less than "how much effort does this take?" — e.g., comparing a wizard vs. a single-page form for a complex task.

### Choosing the Right Questionnaire

| Situation | Best Choice | Why |
|---|---|---|
| Post-test overall satisfaction | **SUS** | Gold standard; comparable benchmarks |
| Very quick in-app survey | **UMUX-Lite** | 2 questions; minimal disruption |
| After each individual task | **SEQ** | Captures task-level difficulty |
| Comparing cognitive effort of two designs | **NASA-TLX** | Measures workload dimensions |
| Customer loyalty / market positioning | **NPS** | Industry standard for business metrics |
| Tracking satisfaction over time | **SUS** or **UMUX-Lite** | Both have strong retest reliability |
| Only 5 users | **SUS** (directional) | Still useful but treat as signal, not definitive |
| 100+ respondents | **SUS** or **UMUX-Lite** (survey) | Statistical reliability at scale |
