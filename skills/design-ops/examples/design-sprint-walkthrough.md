# Design Sprint Walkthrough

Running a 5-day design sprint for a fictional onboarding problem.

---

## Context

**Product:** MealPlan — a meal planning and grocery list app for busy families
**Challenge:** 60% of new users abandon the app before completing onboarding. The team has ideas but no consensus on the right approach. Engineering is about to commit 2 months to building onboarding v2.
**Why a sprint:** High stakes (2 months of engineering), high uncertainty (multiple competing ideas), need evidence before committing.

---

## Pre-Sprint

### Team Assembled

| Name | Role | Why They're Here |
|------|------|-----------------|
| **Maria** (PM) | Decider | Owns the product roadmap. Can commit engineering resources |
| **Jake** (Designer) | Facilitator + Designer | Running the sprint. Will build the prototype |
| **Priya** (Engineer) | Feasibility | Knows what's technically realistic. Built onboarding v1 |
| **Carlos** (Data) | Domain expert | Has the analytics. Knows exactly where users drop off |
| **Nadia** (Support) | Domain expert | Talks to frustrated users daily. Knows the complaints |

### Logistics

- **Room:** Conference room B, booked Mon-Fri 10am-5pm
- **Materials:** 2 whiteboards, 200 stickies, dot stickers, markers, timer, printer paper
- **Participants:** 5 users recruited for Friday (parents who cook 3+ times/week, installed a cooking or meal app in the past 6 months)
- **Prototype tool:** Figma

---

## Monday: Map

### Long-Term Goal

> "MealPlan helps busy families eat home-cooked meals every weeknight without the stress of planning."

### Sprint Questions

1. Can we get users to their first meal plan in under 3 minutes?
2. Will users provide dietary preferences upfront, or does that feel like too much work?
3. Is the grocery list the hook that makes users come back, or is it the meal suggestions?

### Problem Map

```
[New User Downloads App]
  → Opens app for the first time
    → Sees welcome screen
      → Creates account (email or Google)
        → Dietary preferences screen (6 questions)
          → 🔴 38% drop off here
        → Family size screen
          → Cooking skill screen
            → Generate first meal plan
              → 🔴 22% drop off here (plan feels generic)
            → View grocery list
              → 🔴 Users don't understand how to customize
            → Cook first meal
              → ✅ Users who cook one meal have 4x retention
```

### Expert Interviews

**Carlos (Data):**
- The 6-question dietary preferences screen is the biggest drop-off. Average completion time for the full onboarding is 4 minutes 20 seconds. Users who complete it rate the app 4.2/5. Users who don't — 2.1/5
- Insight: Users who reach the meal plan like it. The problem is getting them there

**Nadia (Support):**
- Top complaint: "The meal plan didn't feel personalized." Second: "I don't have time for all these questions." Third: "I couldn't figure out how to change a meal"
- Insight: There's a tension between personalization (needs data) and speed (questions feel like work)

**Guest expert — Lisa (Nutritionist):**
- Only 2 preferences really matter for a good first plan: allergies and number of servings. Everything else can be refined later
- Insight: We're asking 6 questions when 2 would work for a first plan

### How Might We (Top Voted)

1. HMW get users to a personalized plan with only 2 questions? (12 votes)
2. HMW let users customize the plan by doing, not answering questions? (9 votes)
3. HMW show the value of the grocery list before asking users to set preferences? (7 votes)
4. HMW make the first plan feel personal even with minimal data? (6 votes)

### Target

> **We're focusing on:** The journey from "open app for the first time" to "see a meal plan that feels personal enough to try." Specifically, reducing the preferences barrier while maintaining plan quality.

---

## Tuesday: Sketch

### Lightning Demos

| Presenter | Product | Big Idea |
|-----------|---------|----------|
| Jake | **Spotify** — first-time personalization | Shows 5 artists, asks user to pick 3. Visual, fast, feels like browsing not a form |
| Priya | **Duolingo** — placement test | Makes learning feel like a game. The "test" teaches while it assesses |
| Nadia | **HelloFresh** — meal selection | Shows meals first, lets users pick what looks good. Preferences are inferred, not asked |
| Carlos | **Netflix** — taste profile | Asks "pick a few titles you've enjoyed" — feels like fun, not work. Builds a profile without a form |
| Maria | **Headspace** — 1 min first experience | Gets you meditating in 60 seconds. Full setup happens over the first week, not upfront |

**Big idea captured:** "Show food first, ask questions later" — let users interact with meals and infer preferences from behavior.

### Solution Sketches (5 individual sketches)

**Jake's sketch: "Swipe to Plan"**
- User sees 10 meal photos, swipes right (yes) or left (no) — Tinder-style
- After 10 swipes, app generates a personalized plan
- Allergies asked only if a swiped meal contains common allergens

**Priya's sketch: "Quick Start Template"**
- User picks one of 4 templates: "Family Favorites," "Quick & Easy," "Healthy," "Budget"
- Plan generates instantly from template. User customizes by swapping meals
- Preferences learned from swaps over the first week

**Maria's sketch: "Guided First Meal"**
- Skip all preferences. Show one great-looking meal with a recipe
- After cooking it: "Want a full week of meals like this? Let's set up your plan"
- Hook first, setup second

**Nadia's sketch: "Visual Preferences"**
- Instead of text questions, show grids of food photos
- "Tap meals your family loves" — tap 5-10 photos
- "Any allergies?" — single multi-select
- Plan generated from food photos selected

**Carlos's sketch: "Progressive Profile"**
- 2 questions only: allergies + household size
- Generate a "starter plan" immediately
- Each day, one optional question appears (cooking time, cuisine preference, budget)
- Plan improves gradually over the first week

### Key Ideas Across Sketches

- Everyone favors showing food visually over text-based questions
- 3/5 sketches defer most preferences to after the first plan
- The "meals first, questions later" theme from lightning demos came through strongly

---

## Wednesday: Decide

### Heat Map

Heaviest dot clusters on:
- Nadia's "Visual Preferences" — the photo grid for food selection got 15+ dots
- Carlos's "Progressive Profile" — the "2 questions + starter plan" got 12+ dots
- Jake's "Swipe to Plan" — the swipe mechanic got 10+ dots, but concerns about being gimmicky

### Speed Critique

| Sketch | Standout | Concern |
|--------|----------|---------|
| Jake: Swipe | Fun, engaging, fast | Feels like a dating app — might not be taken seriously for meal planning |
| Priya: Templates | Fastest path to plan. Very practical | "Family Favorites" for who? Might feel generic |
| Maria: First Meal | Strongest hook. Proves value before asking anything | Delays personalization too long. Second session has high churn risk |
| Nadia: Visual | Visual preferences feel engaging, not like a form. Data-rich | Photo selection might be slow on mobile. 10+ taps to select |
| Carlos: Progressive | Fastest to first plan. Respects user's time. Plan improves over time | First plan might feel too generic. "Come back tomorrow for a better plan" is risky |

### Decider's Decision

**Maria chose: A hybrid of Nadia's Visual Preferences + Carlos's Progressive Profile.**

Rationale: "We need the first plan to feel personal — that's what Carlos's data shows. But we need to get there fast — that's what the drop-off data demands. Visual preferences give us rich data in a fun, fast format. Then progressive refinement continues improving without asking users to fill out forms."

### Storyboard (10 frames)

1. **Open app** — Warm welcome screen. "Let's find meals your family will love." One CTA: "Get Started"
2. **Allergies** — "Any allergies in your household?" Multi-select chips: Dairy, Gluten, Nuts, Eggs, Shellfish, Soy, None. 1 tap to 3 taps
3. **Family size** — "How many are you feeding?" Stepper: 1-8. Default: 4
4. **Photo grid** — "Tap meals that look good to you" — Grid of 12 meal photos (diverse cuisines, complexities). User taps 3-5. Each tap adds a subtle heart animation. Progress: "3 of 5 selected"
5. **Generating** — Brief loading animation: "Creating your meal plan..." with a fun illustration of ingredients assembling
6. **Your plan** — Weekly view with 5 dinner meals. Each card shows photo, title, time, servings. Header: "Your Starter Plan — swipe any meal to swap it"
7. **Swap interaction** — User taps a meal they don't like → slides out, 3 alternatives slide in → tap to select. The app learns from swaps
8. **Grocery list** — "Your grocery list is ready" — organized by store section. Badge shows "23 items for 5 meals"
9. **Cook prompt** — Next day notification: "Tonight's meal: Chicken Stir Fry. Ready in 25 min." Deep link to recipe
10. **Progressive question** — After cooking first meal: "How'd it go? Quick question to improve next week's plan" — one refinement question (cooking time preference)

---

## Thursday: Prototype

### Team Roles

| Role | Person | Building |
|------|--------|---------|
| Maker 1 | Jake | Screens 1-5 (onboarding flow) |
| Maker 2 | Priya | Screens 6-8 (plan, swap, grocery list) |
| Stitcher | Jake | Connecting all screens, checking transitions |
| Writer | Nadia | All copy — welcome text, meal names, button labels, grocery items |
| Asset collector | Carlos | Meal photos (from Unsplash), icons, placeholder data |
| Interview prep | Maria | Writing interview script, setting up observation room |

### Prototype Details

- **Tool:** Figma with prototype interactions
- **Fidelity:** High visual (real photos, real copy, real layout) with simplified interactions (tap targets, not real swiping)
- **Scope:** Frames 1-8 fully interactive. Frames 9-10 shown as static concept screens
- **Meal data:** 12 real meals for the photo grid, 5 for the plan, 9 alternatives for swaps. All with real recipe names, times, and photos

### End-of-Day Run-Through

- [x] Full flow works: welcome → allergies → family size → photo grid → generating → plan → swap → grocery list
- [x] Real copy throughout (Nadia wrote all of it)
- [x] Meal photos look appetizing and diverse (Carlos sourced 30, selected 26)
- [x] Swap interaction works (tap to reveal alternatives, tap to select)
- [x] One issue found: the "generating" screen felt too fast — couldn't read the text. Added 2-second minimum display time

---

## Friday: Test

### Participant Profiles

| # | Code | Profile |
|---|------|---------|
| P1 | Parent-A | Mother of 2, cooks 4x/week, currently uses paper grocery lists |
| P2 | Parent-B | Father of 3, cooks 2x/week, has tried HelloFresh |
| P3 | Parent-C | Mother of 1 (toddler), cooks daily, uses Pinterest for recipes |
| P4 | Parent-D | Father of 2, partner has nut allergy, cooks 3x/week |
| P5 | Parent-E | Mother of 4, limited cooking time, budget-conscious |

### Observation Grid

| Moment | P1 | P2 | P3 | P4 | P5 |
|--------|----|----|----|----|-----|
| Welcome screen | 🟢 "Oh this is nice" | 🟡 Skimmed quickly | 🟢 Liked the warm tone | 🟢 Clear | 🟡 Wanted to skip ahead |
| Allergies | 🟢 Quick, tapped "None" | 🟢 Easy | 🟡 "Is this just the main ones?" | 🟢 Found nuts immediately | 🟢 Fast |
| Family size | 🟢 Obvious | 🟢 Changed to 5 | 🟢 | 🟢 | 🟢 |
| Photo grid | 🟢 "Oh fun!" Engaged, took time picking | 🟢 "This is better than answering questions" | 🟢 Excited, wanted to pick more than 5 | 🟢 Liked seeing the food | 🟡 "Some of these look expensive" |
| Generating screen | 🟢 Watched the animation | 🟢 Brief anticipation | 🟢 | 🟢 | 🟡 "This is cute but hurry up" |
| Seeing the plan | 🟢 "These actually look good!" | 🟢 Surprised at quality | 🟢 "It remembered I picked Thai food" | 🟢 "No nuts, great" | 🔴 "I don't have time for a 45-min meal on Tuesday" |
| Swap interaction | 🟢 Found it easily | 🟡 Didn't realize could swap at first | 🟢 Loved the alternatives | 🟢 Swapped one meal | 🟢 Swapped to something faster, relieved |
| Grocery list | 🟢 "Oh wow, this is already done?" | 🟢 "This is the killer feature" | 🟢 Liked section grouping | 🟢 Checked for nut items | 🟢 "23 items for 5 meals? That's doable" |

### Patterns

| Pattern | Strength | Insight |
|---------|----------|---------|
| Photo grid was the highlight | 5/5 engaged, 3/5 explicitly praised it | Visual selection is engaging and feels personal, not like a form |
| Grocery list was the "wow" moment | 4/5 surprised and delighted | Users didn't expect a grocery list this fast. This is the hook |
| Swap wasn't immediately discoverable | 2/5 needed a moment to find swap | Need a brief tooltip or animation showing swipeability on first view |
| Plan felt personalized | 4/5 said the plan felt relevant to them | Photo selection + allergies + family size is enough for a good first plan |
| Time/budget info needed on meals | 2/5 mentioned time or cost concerns | Add prep time prominently on meal cards. Consider a "Quick meals" filter |
| Wanted to select more than 5 photos | 2/5 wanted to pick more | Let users pick up to 8. More data = better plan |

### Sprint Decision

**Decision: GO — build it.**

**Reasoning:** 5/5 users completed the flow in under 3 minutes (answering sprint question #1). 4/5 felt the plan was personalized enough to try (answering #2). The grocery list emerged as the retention hook (partially answering #3 — it's the list, not the suggestions). Two adjustments needed: make swap discoverable, add prep time to cards.

**Sprint questions answered:**
1. Can we get users to their first meal plan in under 3 minutes? **Yes — average 2:10**
2. Will users provide dietary preferences upfront? **Yes, when visual. Photo grid averaged 45 seconds and felt fun, not like work**
3. Is the grocery list the hook? **Yes — 4/5 users called it out as the most valuable part**

---

## Next Steps

| Action | Owner | Due |
|--------|-------|-----|
| Share sprint video highlights with full team | Maria | Monday |
| Break the flow into user stories (estimated 3 sprints) | Maria + Priya | Next Wednesday |
| Design the swap discovery tooltip | Jake | Next Tuesday |
| Add prep time to meal card design | Jake | Next Tuesday |
| Plan a follow-up test for the progressive question (frame 10) | Maria | 2 weeks |
| Sprint retro | Jake (facilitator) | Next Friday |

---

## Key Takeaways

1. **Visual preference selection replaced 6 text questions** with a faster, more engaging, and data-richer experience. Users loved it
2. **The "2 questions + photo grid" approach** proved that minimal upfront effort can produce plans that feel personalized
3. **The grocery list was the sleeper hit** — the team was focused on the meal plan, but users were most impressed by the automatic grocery list
4. **Swap discoverability was the only real miss** — easy fix with a tooltip or animation. The sprint caught this before 2 months of engineering
5. **The sprint saved the team from building the wrong thing** — the original plan was to improve the 6-question form. The sprint showed the form was the problem, not the solution
