# Competitive Analysis

How to research, analyze, and position against competitors. Grounded in Jaime Levy's UX Strategy, Jim Kalbach's Jobs to Be Done, and established competitive strategy frameworks.

---

## Why Competitive Analysis Matters

- Learn what has worked and what hasn't — without repeating others' mistakes
- Identify gaps and opportunities the market hasn't addressed
- Understand table-stakes features (what customers expect from everyone)
- Inform value proposition and positioning
- Provide evidence for strategic decisions rather than gut feelings

**When to do it:** Before ideation, before major pivots, and quarterly as maintenance.

---

## Types of Competitors

### Traditional View

| Type | Definition | How to Find |
|------|-----------|-------------|
| **Direct** | Same value proposition to the same customer segment | Search for your product category + "alternatives" |
| **Indirect (same segment)** | Different value proposition to your customers | Ask customers: "What else do you use alongside [our product]?" |
| **Indirect (same value)** | Same value proposition to a different segment | Search for your core function in adjacent markets |

### JTBD View (Kalbach)

Traditional competitive analysis misses the most dangerous competitors: solutions from entirely different categories that get the same job done.

| Competition Level | Example: "Track project progress" |
|------------------|-----------------------------------|
| **Direct** | Asana, Monday.com, Jira |
| **Indirect** | Notion, Confluence (docs with status tracking) |
| **JTBD competitor** | Spreadsheets, email threads, whiteboard photos |

**To find JTBD competitors:** In customer interviews, ask "Before you used [product], how did you get this done?" The answers reveal the real competitive landscape.

### How Many to Analyze

| Category | Count | Why |
|----------|-------|-----|
| Direct | 5-8 | Comprehensive view of your immediate market |
| Indirect | 3-5 | Adjacent opportunities and threats |
| JTBD | 2-3 | Non-obvious substitutes that constrain your strategy |

---

## Research Process (Levy)

### Step 1: Build the Competitor List

Sources:
- Google search for your product category
- App stores (search category and keywords)
- G2, Capterra, Product Hunt (market reviews)
- Customer interviews ("What did you use before?" "What else did you consider?")
- Industry reports and analyst coverage
- Crunchbase for funded startups in your space

### Step 2: Research Each Competitor

For each competitor, gather:

**Business information:**
- Founded when, by whom
- Funding (rounds, amounts, investors)
- Revenue model (subscription, freemium, marketplace, advertising)
- Estimated user base / monthly traffic
- Recent news, pivots, acquisitions

**Product information:**
- Core features and key experience
- Pricing and plans
- Platform coverage (web, mobile, desktop)
- Integration ecosystem
- Content types and personalization

**UX evaluation:**
- Onboarding experience (sign up and try it yourself)
- Core workflow — how many steps to complete the main job?
- Information architecture and navigation
- Visual design quality and consistency
- Accessibility (quick check: keyboard, contrast, screen reader)
- Performance (load time, responsiveness)

**Customer perception:**
- App store ratings and review themes
- G2/Capterra reviews — what do customers praise and complain about?
- Social media sentiment
- Support forums — what issues come up repeatedly?

### Step 3: Build the Comparison Matrix

A matrix with competitors as columns and attributes as rows. Attributes should cover:

| Category | Attributes |
|----------|-----------|
| **Business** | Year founded, funding, revenue model, pricing, market position |
| **Features** | Core features, unique features, missing features |
| **UX quality** | Onboarding ease, core workflow efficiency, visual polish, accessibility |
| **Customer fit** | Target segment, reviews, satisfaction signals |
| **Job performance** | How well does it get the customer's main job done? (Rate 1-5) |

Color-code cells: green (strong), yellow (adequate), red (weak), gray (not available).

### Step 4: Analyze Patterns

Look for:

**Table stakes** — Features every competitor has. These are baseline expectations. You must have them, but they won't differentiate you.

**Differentiators** — Features only 1-2 competitors have that receive positive customer reception. These are opportunities to adopt or outperform.

**Gaps** — Customer needs (from reviews and interviews) that no competitor addresses well. These are your highest-value innovation opportunities.

**Over-served areas** — Features that are heavily invested in across the market but that customers rate as low-importance. Competitors are wasting effort here — you can skip or simplify.

### Step 5: Write the Findings Brief

Structure:
1. **Introduction** — Scope, methodology, competitors analyzed
2. **Market landscape** — Overall positioning map (can be a 2×2 using the two most differentiating dimensions)
3. **Direct competitor analysis** — Key findings for each
4. **Indirect and JTBD analysis** — Non-obvious threats and opportunities
5. **Gaps and opportunities** — What the market isn't doing well
6. **Recommendations** — Your strategic point of view. Take a stand.

---

## Value Innovation

### The Concept (Kim & Mauborgne, via Levy)

Value innovation is the simultaneous pursuit of **differentiation** (offering something new) and **low cost** (reducing or eliminating features the market over-invests in). The goal: make the competition irrelevant by creating new market space.

### Four Actions Framework

For each major feature/attribute in the competitive matrix, ask:

| Action | Question | Effect |
|--------|----------|--------|
| **Eliminate** | Which factors that the industry takes for granted should be eliminated? | Reduce cost and complexity |
| **Reduce** | Which factors should be reduced well below the industry standard? | Remove over-investment |
| **Raise** | Which factors should be raised well above the industry standard? | Create differentiation |
| **Create** | Which factors should be created that the industry has never offered? | Open new value |

### Value Innovation Patterns (Levy)

| Pattern | Description | Example |
|---------|------------|---------|
| **New mash-up** | Combine best features from different competitors | Notion = docs + database + wiki + project management |
| **Innovative slice** | Take one aspect of a broad platform and do it radically better | Loom = screen recording pulled out of Zoom/Teams |
| **Consolidation** | Unify disparate experiences into one solution | Stripe = payment processing + billing + fraud + reporting |
| **Two-sided connection** | Bring distinct user segments together | Airbnb = hosts + travelers in a trust-based marketplace |

### Strategy Canvas

A visual tool showing how you compare to competitors across key attributes:

```
High │         ★                    ★
     │    ★              ★
     │              ★         ★
     │         ●    ●              ●
     │    ●              ●
Low  │                         ●
     └──────────────────────────────
       Attr1  Attr2  Attr3  Attr4  Attr5

★ = Your product    ● = Market average
```

Your value curve should cross the market average — high on some attributes, low on others. If your curve mirrors the market, you have no differentiation. If it's consistently higher, your costs are likely unsustainable.

---

## Market Positioning

### Positioning Map

Plot competitors on two dimensions that matter most to customers. Choose dimensions from your JTBD research — the attributes customers actually use to evaluate solutions.

Common dimension pairs:
- Ease of use vs. Power/flexibility
- Price vs. Feature comprehensiveness
- Self-serve vs. High-touch support
- Speed of setup vs. Depth of customization

Look for **empty quadrants** — market positions no one occupies. These may be opportunities or may be empty for good reason (validate before pursuing).

### Positioning Statement

Template:
> For [target customer segment] who [key need/job to be done], [product name] is a [category] that [key differentiator]. Unlike [primary competitor], we [primary advantage].

This should be one sentence. If it takes a paragraph, the positioning isn't clear enough.

---

## Ongoing Competitive Intelligence

Competitive analysis isn't a one-time exercise. Maintain awareness through:

| Activity | Frequency |
|----------|-----------|
| Monitor competitor product updates (changelogs, release notes) | Monthly |
| Read competitor reviews on G2/Capterra for new themes | Quarterly |
| Re-assess competitive matrix | Quarterly |
| Full competitive analysis refresh | Annually or before major pivots |
| Customer interviews asking about alternatives | Continuously (part of weekly interviews) |

### Signals to Watch

- Competitor raises a large funding round → likely expanding into your space
- Competitor acquires a company in an adjacent space → entering new job territory
- Competitor's reviews suddenly improve in an area where you differentiate → your advantage is eroding
- New entrant appears with a novel approach → potential disruptor
- Competitor deprecates a feature your customers rely on → migration opportunity
