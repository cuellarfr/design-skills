# Metrics and Measurement

How to define, track, and act on UX metrics that connect design decisions to business outcomes. Grounded in Google's HEART framework, Teresa Torres's outcome measurement, and Jaime Levy's funnel design.

---

## HEART Framework (Google)

Five categories of user-centered metrics. Don't track all five — select 1-2 most relevant to your current outcome.

### Categories

| Category | What It Measures | When to Prioritize |
|----------|-----------------|-------------------|
| **Happiness** | User attitudes — satisfaction, perceived ease of use, net promoter | When investigating why users leave despite functional product |
| **Engagement** | Depth and frequency of interaction | When building habitual use or increasing feature adoption |
| **Adoption** | New user acquisition and feature uptake | When launching a new product or major feature |
| **Retention** | Users who return and continue using | When fighting churn or proving long-term value |
| **Task Success** | Effectiveness, efficiency, error rate | When optimizing core workflows or reducing support load |

### Goals-Signals-Metrics (GSM) Process

For each HEART category you choose:

**1. Goal** — What outcome does the team want? (Qualitative)
"New users should quickly understand the product's value"

**2. Signal** — What user behavior would indicate success or failure? (Observable)
"Users complete the onboarding tutorial" / "Users reach the 'aha moment' feature"

**3. Metric** — How to measure the signal at scale? (Quantitative)
"Percentage of new users who complete onboarding within 24 hours of signup"

### Example: HEART for a SaaS Product

| Category | Goal | Signal | Metric |
|----------|------|--------|--------|
| **Happiness** | Users find the product easy to use | Post-task satisfaction responses | Average satisfaction score (1-7) after core workflow |
| **Engagement** | Users integrate product into daily work | Regular return to core features | Average sessions per user per week |
| **Adoption** | New users discover and try key features | Feature first-use events | % of new users who use [core feature] within 7 days |
| **Retention** | Users continue finding value over time | Sustained active usage | 30-day retention rate (monthly active / total registered) |
| **Task success** | Users complete core workflow efficiently | Workflow completion without errors | Completion rate of [core workflow], median time-on-task |

---

## North Star Metric

### What It Is

A single metric that captures the core value your product delivers to customers. It serves as the focal point for the entire product team.

### Characteristics

A good North Star:
- [ ] Measures **value delivered to customers** (not revenue — revenue is a lagging effect of value)
- [ ] Is a **leading indicator** of long-term business success
- [ ] Can be **directly influenced** by product decisions
- [ ] Is **simple enough** to rally a team around
- [ ] **Increases** when customers get more value (not gameable without delivering value)

### Examples by Product Type

| Product Type | North Star | Why |
|-------------|-----------|-----|
| **Marketplace** | Transactions completed per week | Direct measure of both-sides-of-market value |
| **SaaS tool** | Weekly active teams using core feature | Measures habitual value delivery to the unit that pays |
| **Content platform** | Quality content consumed per user per week | Balances consumption with content worth consuming |
| **Communication** | Messages sent per user per day | Proxy for communication value exchanged |
| **E-commerce** | Purchase completions per week | Direct value transaction |
| **Productivity** | Tasks completed per active user per week | Measures actual work accomplished |

### Input Metrics

The North Star breaks down into input metrics that the team can directly influence:

```
North Star: Weekly active teams using core feature
    |
    ├── Activation: % of new teams completing setup within 48 hours
    ├── Engagement: Average core-feature sessions per team per week
    ├── Adoption: % of team members who have used core feature (breadth)
    └── Retention: % of teams active this week who were active last week
```

Each input metric can have its own sub-metrics (signals) that connect to specific product changes.

---

## Funnel Metrics (Levy)

### The Funnel Matrix

Track users through stages from discovery to advocacy:

| Stage | Definition | Key Metric | Optimization |
|-------|-----------|-----------|--------------|
| **Suspect** | Might need your product | Impressions, site visits | SEO, content, advertising |
| **Lead** | Provides contact information | Signups, email captures | Landing page conversion |
| **Prospect** | Actively trying the product | Trial starts, onboarding starts | Onboarding experience |
| **Customer** | Completes a valuable action | First purchase, plan upgrade | Activation flow, "aha moment" |
| **Repeat user** | Regular product usage | Weekly/monthly active | Engagement loops, habit design |
| **Advocate** | Refers others | Referral invites sent, NPS promoters | Referral program, sharing features |

### AARRR (Pirate Metrics)

| Metric | Question | Typical Measurement |
|--------|----------|-------------------|
| **Acquisition** | How do users find us? | Traffic sources, signup rate by channel |
| **Activation** | Do users have a great first experience? | % completing onboarding, reaching "aha moment" |
| **Retention** | Do users come back? | Day-1, Day-7, Day-30 retention rates |
| **Revenue** | Do users pay? | Conversion to paid, ARPU, LTV |
| **Referral** | Do users tell others? | Viral coefficient, referral conversion |

### Where Strategy Focuses

Strategy work primarily concerns **activation** and **retention** — these are where product decisions have the most leverage. Acquisition and revenue are important but more influenced by marketing and pricing than by UX strategy.

---

## Connecting Metrics to Outcomes

### The Metrics Tree

```
Business Outcome: Increase annual recurring revenue (ARR)
    |
    ├── Product Outcome: Increase enterprise trial-to-paid conversion
    │   |
    │   ├── Input: % of trial teams that complete setup
    │   ├── Input: % of trial teams that reach "aha moment"
    │   └── Input: % of trial teams that add 3+ users
    │
    └── Product Outcome: Reduce enterprise churn
        |
        ├── Input: % of accounts using core feature weekly
        ├── Input: NPS score for enterprise segment
        └── Input: Support ticket volume per account
```

Each input metric connects to a specific product lever the team can pull. This creates traceability from a design change to a business outcome.

### Measuring Impact (Torres)

When a solution ships, close the loop:

1. **Instrument the product** for the metrics defined during strategy
2. **Measure people, not actions**: "500 users completed onboarding" > "1,200 onboarding actions occurred"
3. **Measure impact on the desired outcome**, not just feature usage: Did the feature actually move the needle?
4. **Feed learnings back into discovery**: Partial success reveals new opportunities. Failure points back to the opportunity map

### Anti-patterns

| Anti-pattern | Problem | Fix |
|-------------|---------|-----|
| Measuring everything | Noise drowns signal. Team doesn't know what matters | Pick 1-2 HEART categories and 3-5 input metrics |
| Vanity metrics | High numbers that don't indicate value (page views, total signups) | Measure active usage, task completion, retention |
| Measuring only after launch | No baseline. Can't tell if things improved | Define metrics and collect baseline during strategy phase |
| Counting actions instead of people | One power user inflates numbers | Report unique users, not event counts |
| Setting targets without baselines | "Increase by 20%" — 20% of what? | Measure current state for 2-4 weeks before setting targets |
| Measuring feature adoption as success | Feature might be adopted but not move the outcome | Always connect feature metrics to outcome metrics |

---

## Instrumentation Checklist

Before shipping a feature, ensure these are in place:

- [ ] **Outcome metric** defined and baseline measured
- [ ] **Success criteria** stated as specific numbers ("7 out of 10 new users will complete setup within 24 hours")
- [ ] **Events instrumented** for key interactions (not every click — just the signals that matter)
- [ ] **Cohort tracking** enabled (compare behavior of users who got the feature vs. those who didn't)
- [ ] **Time window** defined for evaluation ("We'll measure for 4 weeks before drawing conclusions")
- [ ] **Segment definitions** clear (new vs. existing users, free vs. paid, enterprise vs. SMB)
- [ ] **Dashboard or report** created and shared with the team

---

## Benchmarks

Use these as starting points — actual targets depend on product, market, and maturity:

| Metric | Good | Great | Source/Notes |
|--------|------|-------|-------------|
| Day-1 retention (mobile app) | 25% | 40%+ | Industry average varies by category |
| Day-30 retention (SaaS) | 20% | 35%+ | Enterprise tends higher than SMB |
| Onboarding completion | 40% | 65%+ | Depends on onboarding length |
| Trial-to-paid conversion | 3-5% | 10%+ | Freemium model benchmarks |
| NPS (SaaS) | 30 | 50+ | Above 0 is "good," above 50 is "excellent" |
| Task completion rate | 78% | 90%+ | Nielsen Norman Group usability benchmarks |
| SUS score | 68 (above average) | 80+ (excellent) | Scale: 0-100, average ~68 |
| Time-on-task | — | — | Baseline-relative. 20% improvement is meaningful |

These benchmarks are reference points, not goals. Your goals should come from your outcome and baseline measurements.
