# Design Skills for Claude Code

A collection of UX and design skills for [Claude Code](https://docs.anthropic.com/en/docs/claude-code). These skills give Claude deep knowledge of established design frameworks, heuristics, and methodologies — turning it into an informed design partner rather than a generic assistant.

Each skill follows the same architecture: a main `SKILL.md` file that works standalone, plus `references/`, `templates/`, and `examples/` directories that provide depth on demand.

## Skills

### UX Research
Plan, conduct, and analyze user research using proven methodologies.

Covers generative, evaluative, and continuous discovery research. Includes interview scripting, deep listening for empathy development, usability test planning, participant recruiting, qualitative analysis (affinity diagrams, thematic analysis, behavioral audience segments), and synthesis into personas, journey maps, and opportunity maps.

**Key references:** 20+ research methods catalog (with expanded card sorting: exploratory and statistical analysis, dendrograms, content selection, applying results to IA), interviewing techniques and deep listening, usability testing with SUS scoring (full 10-question scale, scoring formula, grade interpretation), workshop facilitation methods (HMW, Creative Matrix, Dot Voting, and 12 more), continuous discovery (Opportunity Solution Trees, assumption testing).

`14 files` · `~3,800 lines`

### Design Critique & Evaluation
Evaluate UI designs against usability heuristics, UX laws, interaction patterns, interaction design principles, information architecture, and content quality.

Provides a structured 9-step critique framework grounded in Nielsen's 10 heuristics, 27 UX laws organized by design domain, established usability checks, interaction design principles (product posture, perpetual intermediates, excise audits, orchestration), information architecture evaluation (organization, labeling, navigation, search systems), and UX writing review (usable/useful/responsible lenses, error messages, voice and tone).

**Key references:** 50+ interaction patterns catalog with use/don't-use guidance, heuristics and laws deep reference, visual design principles (hierarchy, typography, color, spacing), interaction design principles, IA evaluation (four systems, labeling critique, quick diagnostic), content and UX writing evaluation.

`10 files` · `~3,100 lines`

### Accessibility Audit
Conduct accessibility audits against WCAG 2.2 guidelines.

A 5-layer audit process (automated, keyboard, screen reader, visual, flow) covering conformance at A, AA, and AAA levels. Identifies issues, assesses severity, provides code fixes, and generates audit reports.

**Key references:** Complete WCAG 2.2 checklist reorganized into 11 audit task groups, 15 common issues with before/after code examples, testing tools comparison (axe, WAVE, Lighthouse, Pa11y), CI/CD integration code, keyboard and screen reader test scripts.

`8 files` · `2,175 lines`

### Journey Mapping
Create customer journey maps, service blueprints, experience maps, empathy maps, and other alignment diagrams.

Guides diagram type selection across 7 diagram types, content structure, illustration syntax, alignment workshops, and strategic use of diagrams. Grounded in established alignment diagram methodology, Polaine, Løvlie & Reason's service design framework, and Kalbach's mapping methodology.

**Key references:** Customer journey maps (8 required + 7 optional elements), service blueprints (5 swimlanes, 3 lines, blueprint slices, SERVQUAL/RATER measurement), experience types (transactional/continuous/transformational), service ecology mapping, user story maps (backbone, vertical slicing, walking skeleton), experience prototyping (3 fidelity levels), expectation gap analysis, time as a design object, experience maps and mental models, strategic diagram use (five value types, employee experience alignment, current vs. future state mapping), alignment workshop facilitation (half-day, full-day, and strategic extension formats), JJG's Visual Vocabulary for flow diagramming (complete symbol set, diagram types, pairing patterns with alignment diagrams).

`11 files` · `~3,600 lines`

### Design Systems
Build, document, and maintain design systems with design tokens, component specifications, pattern libraries, naming conventions, and governance processes.

Covers the full lifecycle of design systems — from interface inventory and consolidation through token architecture, component hierarchy, pattern documentation, and long-term governance. Grounded in Atomic Design methodology, pattern-driven approaches, and real-world systems.

**Key references:** Component hierarchy (atoms through pages), 3-tier design token architecture with W3C format, pattern documentation standards, governance models (centralized/federated/hybrid), perceptual patterns (color systems, typography scales, spacing, motion, voice & tone), system maturity model (5 levels).

`13 files` · `~4,500 lines`

### UX Strategy
Connect design decisions to business outcomes through competitive analysis, opportunity mapping, Jobs to Be Done, outcome-driven discovery, and UX metrics.

Covers the full strategy process — from framing business context through customer discovery, competitive positioning, value proposition design, hypothesis-driven validation, outcome measurement, and ethical responsibility. Integrates Opportunity Solution Trees, JTBD job mapping, HEART framework, Lean UX principles, and Papanek's design responsibility framework.

**Key references:** Outcomes and continuous discovery (OSTs, product trio, interview cadence), competitive analysis (matrix, value innovation, four actions framework, market positioning, competitive briefs), Jobs to Be Done (job mapping, desired outcomes, four forces of switching, JTBD personas), metrics (HEART, North Star, funnel metrics, instrumentation), value proposition design (validation hierarchy, Lean UX loop, MVP strategy, business model alignment), ethical and responsible strategy (harm/access/sustainability checks, shared value creation, designing for underserved populations, ethical assumption testing).

`14 files` · `~6,000 lines`

### Interaction Design
Design microinteractions, product behavior, state machines, motion, and error prevention for digital products.

Covers the full interaction design process — from microinteraction specification (trigger → rules → feedback → loops/modes) through product posture analysis, narrative structure (storymapping), state inventory audits, excise elimination, motion design, and error prevention hierarchies. Grounded in Cooper's About Face methodology, Saffer's microinteraction framework, and Lichaw's narrative arc approach.

**Key references:** Microinteraction four-part framework (triggers, rules, feedback, loops/modes), product postures (sovereign/transient/daemonic), perpetual intermediates, narrative structure in product design (three story types, storymapping, peak-end rule), orchestration and flow, excise types (navigational/modal/cognitive/physical), state design (12 states per element), motion principles (Disney-adapted for UI, timing/easing guidelines), error prevention hierarchy (6 levels), undo patterns, loading patterns, recovery flows.

`12 files` · `~5,500 lines`

### Design Ops & Handoff
Run design sprints, manage design-to-development handoff, establish team rituals, documentation standards, and design QA processes.

Covers the operational side of design — how teams organize work, collaborate with engineering, and ship quality. From 5-day design sprints through handoff specs, critique facilitation, documentation standards, visual QA processes, and scaled-down methods for lean teams. Grounded in Knapp's Sprint methodology, Buley's UX team-of-one framework, and real-world design ops practice.

**Key references:** Design sprints (5-day structure, team roles, remote/mini variations, post-sprint actions), handoff process (maturity levels, complete handoff checklist, annotation standards, spec formats, conflict resolution), team rituals (critique, design-eng sync, design review, retro, cadence planning), documentation standards (file organization, naming conventions, versioning, decision records), design QA (detailed checklist, severity scale, issue filing, acceptance criteria, automated visual regression), scaled-down operations (guerrilla methods, adapted rituals for solo designers, UX advocacy, small wins strategy).

`12 files` · `~6,000 lines`

### Design Elevation
Transforms functional visual outputs into polished, professional designs.

Systematically elevates any visual output — dashboards, presentations, reports, web pages, data visualizations — from functional to refined. Built on Tailwind CSS as the canonical design token system, structured through Alla Kholmatova's functional patterns (what users interact with) and perceptual patterns (how the design feels) framework, with data visualization principles grounded in Edward Tufte's work.

**Key references:** Elevation protocol (8-phase systematic process), data visualization principles (data-ink ratio, chartjunk elimination, small multiples, micro/macro readings, layering and separation, graphical integrity), chart selection framework (9 data relationships, 20+ chart types with specific rules), Tailwind-native color systems (categorical, sequential, diverging palettes), typography scales (7 modular scales with context guidance), spacing systems, grid systems (dashboard, magazine, presentation, document), design interrogation checklist (70+ questions across typography, color, layout, data visualization), technique catalog (25+ named techniques), design exemplars (Stripe, Linear, Apple, Swiss Style).

`10 files` · `~3,800 lines`

## Installation

### Install all skills

```bash
# Clone the repo
git clone https://github.com/cuellarfr/design-skills.git

# Copy all skills to your Claude Code skills directory
cp -r design-skills/*/ ~/.claude/skills/
```

### Install a single skill

```bash
# Example: install only the design critique skill
cp -r design-skills/design-critique ~/.claude/skills/
```

### Verify installation

Skills are automatically detected by Claude Code. After copying, start a new conversation and the skills will appear in the available skills list. You can verify by asking Claude:

```
What design skills do you have available?
```

## Skill Architecture

Each skill follows a consistent structure:

```
skill-name/
├── SKILL.md              # Main skill file (200-350 lines)
│                          # Standalone — works without reference files
│                          # Contains frameworks, tables, checklists, quick references
│
├── references/            # Deep reference material (loaded on demand)
│   ├── topic-a.md         # Detailed coverage of a specific area
│   └── topic-b.md         # Each file is self-contained
│
├── templates/             # Fillable templates for deliverables
│   ├── report-template.md
│   └── checklist-template.md
│
└── examples/              # End-to-end walkthroughs
    ├── walkthrough.md      # Full worked example with fictional product
    └── scenarios.md        # Decision scenarios with rationale
```

**Design principles for these skills:**
- **Opinionated defaults** — Specific numbers, benchmarks, and rubrics rather than "consider..." language
- **Actionable over theoretical** — Every principle includes a concrete recommendation
- **Before/after examples** — Show what bad and good look like, with scoring
- **Progressive depth** — Main file is comprehensive standalone; reference files go deeper
- **Grounded in sources** — Built from established books and frameworks, not invented heuristics

## Sources

These skills synthesize material from established books, frameworks, and standards:

### Books

- **About Face** (Alan Cooper) — Product postures, perpetual intermediates, excise elimination, orchestration, considerate software, goal-directed design
- **Atomic Design** (Brad Frost) — Five-level component hierarchy, pattern lab, interface inventories
- **Blue Ocean Strategy** (W. Chan Kim & Renée Mauborgne) — Value innovation, four actions framework, strategy canvas
- **Card Sorting** (Donna Spencer) — Open/closed/hybrid sorts, exploratory and statistical analysis, dendrograms, applying results to IA
- **Continuous Discovery Habits** (Teresa Torres) — Opportunity Solution Trees, story-based interviewing, assumption testing, product trio
- **Design for the Real World** (Victor Papanek) — Ethical responsibility, shared value creation, designing for underserved populations
- **Design Systems** (Alla Kholmatova) — Functional and perceptual patterns, shared language, pattern lifecycle
- **Don't Make Me Think** (Steve Krug) — Usability testing, self-evident design, trunk test
- **Information Architecture** (Rosenfeld, Morville & Arango) — Organization, labeling, navigation, and search systems, IA evaluation
- **A Visual Vocabulary for Information Architecture and Interaction Design** (Jesse James Garrett) — Standard notation for site diagrams, flow diagramming, decision points, conditional selectors
- **Jobs to Be Done** (Jim Kalbach) — Job mapping, desired outcomes, switch interviews, four forces, JTBD personas
- **Lean UX** (Jeff Gothelf & Josh Seiden) — Hypothesis-driven design, outcomes over outputs, MVP strategy, proto-personas
- **Mapping Experiences** (Jim Kalbach) — Strategic use of alignment diagrams, five value types, current vs. future state mapping, workshop facilitation
- **Microinteractions** (Dan Saffer) — Four-part framework (trigger/rules/feedback/loops), signature moments, long wow lifecycle
- **Modular Web Design** (Nathan Curtis) — Design system governance, contribution models, adoption strategies
- **Outcome-Driven Innovation** (Tony Ulwick) — Desired outcome statements, importance-satisfaction framework, opportunity scoring
- **Practical Empathy** (Indi Young) — Deep listening, cognitive empathy, behavioral audience segments, guiding principles
- **Service Design** (Andrew Polaine, Lavrans Løvlie, Ben Reason) — Service ecologies, blueprints, experience types, SERVQUAL/RATER, experience prototyping, co-production
- **Sprint** (Jake Knapp, John Zeratsky, Braden Kowitz) — 5-day design sprint methodology, team roles, prototyping, user testing with 5 participants
- **The Innovator's Dilemma** (Clayton Christensen) — Disruptive innovation theory, jobs-to-be-done origin
- **The User Experience Team of One** (Leah Buley) — Guerrilla methods, UX advocacy, scaled-down operations for lean teams
- **The User's Journey** (Donna Lichaw) — Narrative arc, storymapping, concept/origin/usage stories, peak-end design
- **User Story Mapping** (Jeff Patton) — Backbone, walking skeleton, vertical slicing, release planning
- **UX Strategy** (Jaime Levy) — Competitive analysis, value innovation, funnel design, guerrilla research
- **The Visual Display of Quantitative Information** (Edward Tufte) — Data-ink ratio, graphical integrity, chartjunk elimination, small multiples, data density, aesthetics and technique
- **Envisioning Information** (Edward Tufte) — Escaping flatland, micro/macro readings, layering and separation, small multiples, color and information, narratives of space and time
- **Writing Is Designing** (Michael J. Metts & Andy Welfle) — UX writing as design, usable/useful/responsible lenses, voice and tone, content critique

### Frameworks & Methodologies

- **Alignment diagram methodology** — Journey maps, service blueprints, experience maps, ecosystem models
- **Design ops practice** — Handoff maturity models, design QA processes, team rituals, visual regression testing, documentation standards
- **Disney's 12 Principles of Animation** — Adapted for UI motion design (squash/stretch, anticipation, follow-through, easing)
- **Four Forces of Switching** (Bob Moesta) — Push, pull, anxiety, habit — forces that drive or prevent product adoption
- **HEART Framework** (Google) — Happiness, Engagement, Adoption, Retention, Task Success metrics
- **Laws of UX** (lawsofux.com) — 27 UX laws organized by design domain (Hick's, Fitts's, Jakob's, Miller's, and more)
- **LUMA Institute methods** — Workshop facilitation techniques (HMW, Creative Matrix, Dot Voting)
- **Nielsen's 10 Usability Heuristics** — Heuristic evaluation framework and severity scales
- **Service design principles** — Touchpoints, co-production, service ecology
- **Statecharts** (David Harel) — Parallel states, nested states, UI state modeling
- **System Usability Scale (SUS)** — Standardized usability questionnaire and scoring methodology

### Standards & Design Systems

- **Apple Human Interface Guidelines** — Platform conventions for motion, input, navigation, and layout
- **Material Design 3** (Google) — Motion system, component specs, adaptive design, color system
- **Polaris** (Shopify), **Carbon** (IBM), **Spectrum** (Adobe), **Lightning** (Salesforce) — Real-world design system references
- **W3C Design Tokens Community Group** — Token format specification, type system, alias syntax
- **Tailwind CSS** — Design token system (colors, spacing, typography, shadows, border radius)
- **WCAG 2.2** — Web Content Accessibility Guidelines (A, AA, AAA conformance levels)
- **WebAIM** — Million report data, contrast requirements, testing tools

### Design Traditions

- **Bauhaus** — Form follows function, geometric fundamentals, systematic design thinking
- **Swiss / International Typographic Style** — Grid systems, typographic hierarchy, objective visual communication

## License

MIT
