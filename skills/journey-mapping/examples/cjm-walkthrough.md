# From Research to Journey Map: A Walkthrough

This example walks through the complete process of building a customer journey map, using a fictional scenario: mapping the onboarding experience for "FreshBooks," a freelancer accounting tool.

---

## Context

**Persona:** Alex, freelance graphic designer, 2 years freelancing, uses spreadsheets for invoicing
**Scenario:** Switching from spreadsheets to FreshBooks for invoicing and expense tracking
**Scope:** From first hearing about FreshBooks → completing first real invoice
**Map type:** Current state
**Based on:** 6 user interviews with recent signups (within 30 days)

---

## Step 1: Research Excerpts

### P1 — Freelance photographer, 3 weeks in

> "My accountant told me I needed to stop using spreadsheets. She specifically recommended FreshBooks or QuickBooks. I googled both and FreshBooks looked simpler, which is what I wanted."

> "Signing up was fine, but then I hit this dashboard with all these modules — invoicing, expenses, time tracking, projects, reports — and I didn't know where to start. I just wanted to send an invoice."

> "I spent about 20 minutes setting up my first invoice template. The preview looked professional, which made me feel like this was worth it."

### P2 — Freelance writer, 1 week in

> "I found FreshBooks through a blog post about freelancer tools. The pricing page confused me though — I couldn't tell the difference between Lite and Plus. I picked Lite because it was cheaper."

> "The first thing I tried to do was import my client list from my spreadsheet. I couldn't figure out how. I ended up adding each client manually, which took forever."

> "I still haven't figured out the expense tracking. I'm doing that in my spreadsheet still."

### P3 — Freelance developer, 2 weeks in

> "I signed up for the free trial to test it. The onboarding asked me a bunch of questions about my business — revenue range, number of employees, industry. Felt like overkill for a solo freelancer."

> "Once I got to the invoice editor, it was actually really intuitive. Took me maybe 5 minutes to create my first invoice. The client got it and paid within a day — that was a great moment."

> "The mobile app is rough though. I tried to log an expense from my phone and gave up."

---

## Step 2: Extract Observations

| # | Observation | Source | Phase |
|---|---|---|---|
| 1 | Discovered through accountant recommendation | P1 | Awareness |
| 2 | Discovered through blog post | P2 | Awareness |
| 3 | Compared FreshBooks to QuickBooks — chose FreshBooks for simplicity | P1 | Research |
| 4 | Pricing page was confusing — couldn't distinguish plan tiers | P2 | Research |
| 5 | Signed up for free trial to test before committing | P3 | Signup |
| 6 | Onboarding questions felt like overkill for solo freelancer | P3 | Setup |
| 7 | Dashboard overwhelm — too many modules, didn't know where to start | P1 | Setup |
| 8 | Couldn't import client list from spreadsheet | P2 | Setup |
| 9 | Added clients manually — tedious and time-consuming | P2 | Setup |
| 10 | Invoice template setup took 20 min but result looked professional | P1 | First Use |
| 11 | Invoice editor was intuitive — 5 min to first invoice | P3 | First Use |
| 12 | Client paid within a day — high point of experience | P3 | First Use |
| 13 | Expense tracking not discovered or abandoned | P2, P3 | Expansion |
| 14 | Mobile app for expenses was frustrating — gave up | P3 | Expansion |
| 15 | Still using spreadsheet for expenses alongside FreshBooks | P2 | Expansion |

---

## Step 3: Define Phases

Based on the data, five phases emerge:

1. **Awareness** — Freelancer learns FreshBooks exists
2. **Evaluation** — Compares options, reviews pricing
3. **Setup** — Signs up, configures account, adds clients
4. **First Invoice** — Creates and sends first real invoice
5. **Expansion** — Explores additional features (expenses, reports)

---

## Step 4: Build the Journey Map

### Phase 1: Awareness

**Goal:** Find a better way to handle invoicing than spreadsheets

**Actions:**
- Receives recommendation from accountant or colleague
- Reads blog post or review about freelancer tools
- Searches Google for "invoicing tool for freelancers"

**Touchpoints:**
- Word of mouth, blog posts, Google search results, review sites

**Thinking:**
- "Is my spreadsheet really that bad?"
- "Which tools do other freelancers actually use?"
- "Do I really need to pay for this?"

**Feeling:** Curious but skeptical — Sentiment: 🙂

**Pain Points:**
- Relying on scattered recommendations with no clear comparison

**Opportunities:**
- Surface comparison content targeting "spreadsheet to invoicing tool" searches
- Leverage referral program through accountant partnerships

**Ownership:** Marketing

---

### Phase 2: Evaluation

**Goal:** Choose the right tool and plan

**Actions:**
- Visits FreshBooks website and competitor sites
- Compares pricing pages side by side
- Reads feature comparison tables
- Checks for free trial availability

**Touchpoints:**
- Marketing website, pricing page, comparison pages, review sites

**Thinking:**
- "What's the difference between Lite and Plus?"
- "Will this work for just me, or is it designed for bigger businesses?"
- "Can I try it before committing?"

**Feeling:** Confused by pricing, reassured by free trial — Sentiment: 😐

**Pain Points:**
- Parsing pricing tiers that aren't clearly differentiated (4/6 participants)
- Feature descriptions using accounting jargon freelancers don't understand

**Opportunities:**
- Simplify pricing page with persona-based recommendations ("Solo freelancer? Start here")
- Add plain-language feature descriptions

**Ownership:** Marketing / Product Marketing

---

### Phase 3: Setup

**Goal:** Get the account ready to send the first invoice

**Actions:**
- Signs up for free trial
- Answers onboarding questions (business info, revenue, industry)
- Lands on dashboard and tries to orient
- Attempts to import or manually add client list
- Customizes invoice template

**Touchpoints:**
- Signup flow, onboarding wizard, dashboard, client management, invoice settings

**Thinking:**
- "Why do they need my revenue range? I'm just one person"
- "There are so many options on this dashboard — where do I start?"
- "How do I get my existing clients in here?"

**Feeling:** Overwhelmed, slightly frustrated — Sentiment: 😟

**Pain Points:**
- Onboarding questions feel irrelevant for solo freelancers (3/6 participants)
- Dashboard presents all features at once — no guided path (4/6 participants)
- No CSV import for client list (2/6 participants)
- Manual client entry is tedious for anyone with 10+ clients (2/6 participants)

**Opportunities:**
- Add solo/team branching early: skip irrelevant questions for solo users
- Replace dashboard with a guided first-run: "Let's send your first invoice" wizard
- Add CSV import for clients
- Offer to create first client inline during first invoice creation

**Ownership:** Product / Onboarding team

**⭐ Moment of Truth:** Dashboard first impression. If users feel overwhelmed here, they close the tab (2/6 did exactly this).

---

### Phase 4: First Invoice

**Goal:** Create and send a professional invoice to a real client

**Actions:**
- Opens invoice editor
- Fills in client details, line items, payment terms
- Previews the invoice
- Sends to client
- Receives payment

**Touchpoints:**
- Invoice editor, invoice preview, email delivery, payment notification

**Thinking:**
- "Does this look professional enough?"
- "Did my client actually receive it?"
- "That was actually easier than my spreadsheet"

**Feeling:** Satisfied, pleasantly surprised — Sentiment: 😄

**Pain Points:**
- Minor: Some uncertainty about payment terms defaults (1/6 participants)

**Opportunities:**
- Add a "Your first invoice was sent!" celebration moment
- Show invoice open/view tracking ("Your client opened the invoice")

**Ownership:** Product / Invoice team

**⭐ Moment of Truth:** Receiving the first payment through FreshBooks. This is the moment the product proves its value. 3/6 participants specifically mentioned this as the "aha moment."

---

### Phase 5: Expansion

**Goal:** Use FreshBooks for more than just invoicing (expenses, reports)

**Actions:**
- Explores dashboard modules after initial success
- Tries expense tracking (on desktop or mobile)
- Continues using spreadsheet for features not yet adopted

**Touchpoints:**
- Dashboard, expense module, mobile app, reports

**Thinking:**
- "I should probably track my expenses here too..."
- "How does the expense thing work?"
- "The mobile app doesn't seem to work well for this"

**Feeling:** Indifferent, slightly frustrated with mobile — Sentiment: 😐

**Pain Points:**
- Expense tracking not naturally discoverable after invoicing success (4/6 participants)
- Mobile app expense entry is clunky (2/6 participants)
- No prompt or guidance to explore features beyond invoicing
- Users satisfice: invoicing works, so they stop exploring

**Opportunities:**
- After first paid invoice, prompt: "Want to track the expenses for this project too?"
- Improve mobile expense capture (photo receipt → auto-categorize)
- Progressive feature introduction at day 7 and day 14

**Ownership:** Product / Growth team

---

## Step 5: Sentiment Curve

| Awareness | Evaluation | Setup | First Invoice | Expansion |
|---|---|---|---|---|
| 🙂 Curious | 😐 Confused | 😟 Overwhelmed | 😄 Satisfied | 😐 Stalled |

**Peak:** First invoice paid — the moment the product proves its value
**Valley:** Dashboard first impression — information overload with no guided path

---

## Step 6: Prioritized Opportunities

| # | Phase | Opportunity | User Impact | Freq. | Biz Impact | Effort | Score |
|---|---|---|---|---|---|---|---|
| 1 | Setup | Replace dashboard with guided "Send your first invoice" wizard | 5 | 4 | 5 | 3 | 4.7 |
| 2 | Setup | Add solo freelancer path in onboarding | 4 | 3 | 4 | 2 | 5.5 |
| 3 | Expansion | Contextual feature prompts after first success | 4 | 4 | 5 | 2 | 6.5 |
| 4 | Evaluation | Simplify pricing page with persona-based recommendations | 3 | 4 | 4 | 1 | 11.0 |
| 5 | Setup | Add CSV import for clients | 3 | 2 | 2 | 2 | 3.5 |
| 6 | Expansion | Improve mobile expense capture | 3 | 2 | 3 | 4 | 2.0 |

---

## Step 7: What Made This Map Effective

1. **Started with research, not assumptions** — Every element traces to interview data
2. **Used story-based interview questions** — "Walk me through what happened" yielded rich behavioral data
3. **One persona, one scenario** — Focused scope made every insight actionable
4. **Consistent syntax** — Actions start with verbs, thoughts are questions, feelings are adjectives
5. **Moments of truth flagged** — The team knows where to focus design effort
6. **Sentiment curve is scannable** — The emotional arc tells the story at a glance
7. **Opportunities are scored and prioritized** — Not a wish list, but a ranked plan
8. **Pain point frequency noted** — "4/6 participants" is more compelling than "some users"
