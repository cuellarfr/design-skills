# Diagram Selection Scenarios

Real-world scenarios showing which alignment diagram to use and why. For each situation, we explain the decision rationale and the expected output.

---

## Scenario 1: "We need to improve our onboarding experience"

**Context:** Analytics show 50% of users drop off during onboarding. The team has some hypotheses but hasn't mapped the experience.

**Recommended diagram:** Customer Journey Map (current state)

**Why CJM?** You need to understand the user's emotional experience at each step. Where do they get confused? Where do they feel overwhelmed? The emotional layer of a CJM is what separates it from a simple user flow — and emotions are what drive drop-off.

**Why not a service blueprint?** A blueprint would show how the organization delivers onboarding, which is useful — but first you need to understand the customer experience. Map the journey first, then blueprint the operations behind it if needed.

**Process:**
1. Interview 5-6 recent signups (within 30 days)
2. Review analytics: step-by-step conversion funnel
3. Map the journey from "first hear about us" to "first meaningful use"
4. Prioritize pain points by severity and frequency

**Expected output:** 5-7 phase CJM with sentiment curve, prioritized pain points, and opportunities

**Timeline:** 2-3 weeks

---

## Scenario 2: "Our support team and product team aren't aligned"

**Context:** Support keeps getting tickets about problems the product team doesn't know about. Product ships features without telling support. Customers fall through the cracks between teams.

**Recommended diagram:** Service Blueprint

**Why a blueprint?** This is a coordination problem. The customer experience suffers because of disconnected internal operations. A blueprint makes the backstage visible and shows where handoffs fail.

**Why not a journey map?** A journey map would only show the customer's side. You need to see what's happening behind the scenes — who does what, when, and how teams (don't) communicate.

**Process:**
1. Start with a journey map of the most common customer scenario
2. Interview frontline support staff: "Walk me through what happens when a customer reports X"
3. Interview product team: "What do you know about how support handles Y?"
4. Map all five lanes, paying special attention to handoffs

**Expected output:** Blueprint with annotated handoff points, failure points, and wait times

**Timeline:** 2-4 weeks

---

## Scenario 3: "We're exploring a new market and don't know the landscape"

**Context:** The company wants to enter the "freelancer financial management" space but hasn't built anything yet. They need to understand how freelancers manage their finances before designing a product.

**Recommended diagram:** Experience Map

**Why an experience map?** You're not mapping your product's experience — you don't have a product yet. You need to map the broader human activity (financial management for freelancers) to understand where value could be created.

**Why not a CJM?** A CJM is product-specific. An experience map is product-agnostic. You need the latter when you're still exploring the problem space.

**Process:**
1. Interview 8-10 freelancers about how they manage money (not about any specific tool)
2. Include the full lifecycle: earning → invoicing → tracking → taxes → planning
3. Document all tools, workarounds, and pain points — including non-digital ones
4. Identify unmet needs and underserved phases

**Expected output:** Experience map with phases, jobs to be done, pain points, and opportunity areas. Feed into product strategy.

**Timeline:** 3-4 weeks

---

## Scenario 4: "We need a quick way to share what we know about our users"

**Context:** The team just finished a round of user interviews. They need to synthesize and share findings quickly — a full journey map isn't warranted.

**Recommended diagram:** Empathy Map

**Why an empathy map?** It's the fastest alignment diagram to create. You can build one in a 30-minute team exercise. It captures the essential user insight (Says/Does/Thinks/Feels) without the overhead of a full journey map.

**Why not a CJM?** A CJM requires mapping temporal phases and is more effort. If you just need to align the team on "who is this person and what do they need," an empathy map is sufficient.

**Process:**
1. Gather the team (30-60 minutes)
2. For each quadrant, populate with data from recent interviews
3. Synthesize goals and needs in the center
4. Identify the Says/Thinks gap — where what users say differs from what they appear to think

**Expected output:** One empathy map per user segment, with key tensions and design implications

**Timeline:** 1-2 hours

---

## Scenario 5: "We have a complex product with many stakeholders"

**Context:** The product is a B2B platform with buyers, sellers, administrators, and support agents all interacting through different interfaces. The team can't see how all the pieces connect.

**Recommended diagram:** Ecosystem Model

**Why an ecosystem model?** You need to see the big picture: who are all the actors, how do they relate, and what value flows between them. A journey map only shows one actor's path. An ecosystem model shows the whole network.

**Why not a journey map or blueprint?** Those are linear (timeline-based). Your problem is structural — understanding the relationships and dependencies between multiple actors.

**Process:**
1. List all entities: user types, systems, content, third-party services
2. Map relationships: who interacts with whom, and what do they exchange?
3. Identify value flows: money, data, content, trust
4. Flag dependencies and bottlenecks
5. Use concentric rings to show proximity/priority

**Expected output:** Ecosystem model showing all actors, relationships, and value flows. Identifies where value is created and where it breaks down.

**Timeline:** 1-2 weeks

---

## Scenario 6: "We need to understand how our users think about [domain]"

**Context:** The product team is redesigning the navigation for a complex financial planning tool. They need to understand how users mentally organize financial concepts — not how they use the tool, but how they think about money management.

**Recommended diagram:** Mental Model Diagram

**Why a mental model?** Navigation should match how users think, not how the organization is structured. A mental model diagram maps user reasoning from the ground up, revealing the natural categories and hierarchies in users' minds.

**Why not a card sort?** Card sorts are great for testing specific labels, but they start with your categories. A mental model diagram discovers the user's categories.

**Process:**
1. Conduct 15-20 interviews focused on how users think about and organize financial planning
2. Extract tasks, beliefs, and feelings — one per note
3. Build towers (cluster related items) and mental spaces (cluster related towers)
4. Map your product's features below each tower
5. Identify gaps: tall towers with no product support = opportunities

**Expected output:** Mental model diagram with towers, mental spaces, and feature alignment. Gaps inform navigation redesign.

**Timeline:** 4-6 weeks (mental models require more research)

---

## Scenario 7: "We're redesigning a service that spans digital and physical touchpoints"

**Context:** A healthcare clinic wants to improve the patient experience from booking an appointment online to leaving the clinic after a visit. The experience involves website, phone, physical space, staff interactions, and follow-up communications.

**Recommended diagram:** Service Blueprint + Customer Journey Map (combined approach)

**Why both?** The digital and physical touchpoints need to be coordinated. A CJM captures the patient's emotional experience; a blueprint shows how the clinic's operations deliver (or fail to deliver) that experience across channels.

**Process:**
1. Map the patient journey first: booking → arrival → check-in → waiting → consultation → checkout → follow-up
2. Then blueprint the operations: what happens behind the counter at each step?
3. Pay special attention to channel transitions (digital → physical → digital)
4. Shadow clinic staff to understand backstage operations
5. Conduct service safaris (experience the service yourself)

**Expected output:** Combined CJM + blueprint showing both patient experience and operational support. Annotated with pain points, wait times, and channel transitions.

**Timeline:** 3-5 weeks

---

## Scenario 8: "We need to map the journey but we don't have time for research"

**Context:** Stakeholders want a journey map by next week. There's no time for user interviews.

**Recommended approach:** Assumption-Based Journey Map (clearly labeled as such)

**What to do:**
1. Gather the product trio + customer-facing staff (support, sales)
2. Map the journey from collective knowledge in a 2-hour workshop
3. **Label every element as "assumed" or "verified"** — this is critical
4. Use the assumption map to identify the biggest unknowns
5. Plan targeted research to validate the highest-risk assumptions

**What NOT to do:**
- Don't present an assumption-based map as a research-based map
- Don't make major design decisions based on unvalidated assumptions
- Don't skip research permanently — the assumption map should generate a research plan

**Expected output:** Assumption-based CJM with confidence levels marked, plus a research plan for validation

**Timeline:** 1 week (map) + 2 weeks (validation research)

---

## Quick Decision Matrix

| Situation | Start Here | Then Consider |
|---|---|---|
| Improving a specific product experience | Customer Journey Map | Service Blueprint (if operational issues) |
| Departments aren't coordinated | Service Blueprint | Alignment Workshop |
| Exploring a new market | Experience Map | Mental Model Diagram |
| Quick user synthesis | Empathy Map | Journey Map (if deeper dive needed) |
| Complex multi-stakeholder platform | Ecosystem Model | Separate CJMs per actor |
| Understanding user reasoning | Mental Model Diagram | Card Sort (for validation) |
| Service spans digital + physical | CJM + Service Blueprint | Service Safari first |
| No time for research | Assumption-Based CJM | Validation research ASAP |
| Post-launch assessment | CJM with analytics overlay | Service Blueprint for operations |
