# Design Patterns Catalog

A reference of common interaction patterns organized by function. For each pattern: when to use it, when not to, and common misapplications.

---

## Navigation Patterns

### Breadcrumbs
**Use when:** Site has 3+ levels of hierarchy; users arrive via search to deep pages
**Don't use when:** Flat site structure; single-level app
**Misapplication:** Using as primary navigation (supplement only); omitting current page from trail
**UX Laws:** Recognition over Recall (H6), shows user location

### Tabs
**Use when:** 2-5 parallel sections of equal weight; content doesn't need to be compared across tabs
**Don't use when:** Sequential steps (use wizard); more than 7 tabs; tabs that scroll
**Misapplication:** Hiding critical content in non-default tabs; inconsistent tab bar across pages
**UX Laws:** Chunking (organizes content), Jakob's Law (familiar pattern)

### Pagination vs. Continuous Scrolling
**Pagination — Use when:** Users need to return to specific results; total count matters; performance concerns
**Continuous Scrolling — Use when:** Browsing/discovery mode; social feeds; visual content
**Misapplication:** Infinite scroll on e-commerce (users can't bookmark/share position); pagination on feeds
**UX Laws:** Goal-Gradient Effect (pagination shows progress), Working Memory (pagination preserves location)

### Fat Footer
**Use when:** Site has many sections; secondary navigation is needed; SEO benefit
**Don't use when:** Simple app with minimal pages
**UX Laws:** Recognition over Recall (H6), provides site overview

### Categorization
**Use when:** Content has a natural hierarchical structure; users browse by topic
**Don't use when:** Content is flat or highly cross-referenced (use tagging instead)
**Misapplication:** Too many categories (>7 top-level); overlapping categories; deep nesting (>3 levels)
**Also called:** Sections
**UX Laws:** Chunking, Law of Proximity

### Tagging
**Use when:** Content belongs to multiple topics; users think in different terms; bottom-up organization
**Don't use when:** Content has clear hierarchy; tags proliferate without governance
**Misapplication:** Tags as sole navigation (needs fallback); no tag taxonomy or governance
**In contrast to:** Categorization
**UX Laws:** Recognition over Recall (H6), flexibility for different mental models

### Search Filter
**Use when:** Large datasets; users know what they want but need to narrow results; faceted attributes
**Don't use when:** Small datasets (<20 items); results are homogeneous
**Misapplication:** Too many filters visible at once; filters that return zero results without warning; resetting all filters on one change
**Also called:** Faceted Search, Refining Search
**UX Laws:** Hick's Law (reduces choices), Tesler's Law (system helps narrow)

---

## Input Patterns

### Account Registration
**Use when:** Personalized experience is necessary; features require user identity
**Don't use when:** Users need to accomplish tasks immediately; registration can be deferred (use Lazy Registration)
**Misapplication:** Requiring registration before users see value; asking for too much information upfront; no social sign-in options
**Also called:** Sign-In Wall, User Sign-Up
**UX Laws:** Goal-Gradient Effect (blocks progress), Tesler's Law (keep signup minimal)

### Lazy Registration
**Use when:** Users need to experience value before committing; registration friction kills conversion
**Don't use when:** Features fundamentally require identity; security requirements mandate upfront auth
**Misapplication:** Losing user's work when they finally register; unclear what triggers the registration prompt
**Also called:** Immediate Immersion, Gradual Engagement
**UX Laws:** Paradox of Active User (let users act first), Peak-End Rule (positive start)

### Autocomplete
**Use when:** Large dataset of possible values; users know what they want but may misspell; address/location fields
**Don't use when:** Few options (use dropdown); users are exploring (use browse)
**Misapplication:** Results that don't match user's mental model; no keyboard navigation; no "no results" state
**UX Laws:** Recognition over Recall (H6), Fitts's Law (reduces typing)

### Good Defaults
**Use when:** Most users choose the same option; data can be inferred from context
**Don't use when:** No clearly common choice; default could cause errors (e.g., country field in global app)
**Misapplication:** Defaulting to options that benefit the business, not the user (pre-checked marketing opt-in)
**UX Laws:** Tesler's Law (system bears complexity), Parkinson's Law (reduces time)

### Forgiving Format
**Use when:** User input could vary in format (phone numbers, dates, postal codes)
**Don't use when:** Specific format is legally required
**Misapplication:** Showing format requirements but not auto-formatting; rejecting valid input
**UX Laws:** Postel's Law (be liberal in what you accept)

### Structured Format
**Use when:** Input must be in a specific format; breaking into segments aids comprehension
**Don't use when:** Free-text input is more natural; format varies by context
**Misapplication:** Separate fields for area code + phone number (increased effort); rigid date format without date picker
**UX Laws:** Chunking (breaks complex input into segments), Error Prevention (H5)

### Fill in the Blanks
**Use when:** Input has a natural sentence structure; making the form feel conversational
**Don't use when:** Many fields to collect; fields don't form a natural sentence; accessibility is a priority (can confuse screen readers)
**Misapplication:** Long, complex sentences users must parse; mixing languages awkwardly
**UX Laws:** Mental Model (mirrors natural language), H2 (Match Real World)

### Expandable Input
**Use when:** Input length varies; showing a large field upfront wastes space
**Don't use when:** Expected input is always the same length; expansion would displace critical adjacent content
**Misapplication:** Expanding over other interactive elements; no maximum size boundary
**UX Laws:** Tesler's Law (system adapts to content), H8 (Minimalist Design)

### Inplace Editor
**Use when:** Users frequently edit displayed values; context matters for editing; reducing navigation to separate edit screens
**Don't use when:** Complex editing requiring multiple related fields; audit trail is critical
**Misapplication:** No clear visual cue that content is editable; no save/cancel mechanism; losing data on accidental click-away
**Also called:** Direct Manipulation, Inline Editing
**UX Laws:** Direct Manipulation, Fitts's Law (edit where you see)

### Wizard / Steps Left
**Use when:** Complex task with 4+ required stages; clear sequential flow; users need progress feedback
**Don't use when:** Steps aren't sequential; users need to compare across steps; form is short enough for one page
**Misapplication:** Too many steps (each step too small); no way to skip to a specific step; no back button; losing data on back navigation
**UX Laws:** Goal-Gradient Effect, Zeigarnik Effect, Chunking

### Settings / Preferences
**Use when:** Users need to customize product behavior; configuration options exist for different use cases
**Don't use when:** Good defaults eliminate the need; settings are rarely changed (bury deeper)
**Misapplication:** Too many settings (decision fatigue); no explanation of what settings do; settings that require restart with no warning
**UX Laws:** Hick's Law (keep minimal), Tesler's Law (good defaults reduce need)

---

## Content Patterns

### Cards
**Use when:** Displaying collections of varied content (products, articles, users); each item has multiple attributes
**Don't use when:** Simple lists of one attribute; comparison is needed (use table)
**Misapplication:** Cards with too much content (should link to detail); inconsistent card sizes creating visual chaos; clickable area unclear
**UX Laws:** Law of Common Region (each card is a group), Chunking

### Progressive Disclosure
**Use when:** Feature-rich interface; not all information is needed immediately; different user expertise levels
**Don't use when:** All content is equally important; hiding creates confusion about what's available
**Misapplication:** Hiding primary actions (progressive disclosure is for secondary content); too many levels of disclosure
**UX Laws:** Hick's Law (fewer visible options), Cognitive Load (reduce extraneous load)

### Blank Slate / Empty State
**Use when:** User has no content yet; first-time experience; after deleting all items
**Don't use when:** Content should always exist (pre-populate with defaults)
**Misapplication:** Just showing "No items" without guidance; missing opportunity to educate and motivate
**Best practice:** Show illustration + explanation + primary action ("Create your first project")
**UX Laws:** Paradox of Active User (guide immediately), Goal-Gradient Effect (give a head start)

### Dashboard
**Use when:** Users need real-time overview of key metrics; multiple data sources need monitoring
**Don't use when:** Users only care about one metric; data doesn't change frequently
**Misapplication:** Too many metrics (information overload); no hierarchy (all widgets same size); no actionable insight
**UX Laws:** Miller's Law (chunk into sections), Visual Hierarchy, Selective Attention

### Event Calendar
**Use when:** Content is time-based; users need to see temporal relationships; scheduling is involved
**Don't use when:** Events are sparse; timeline is more appropriate; users think in lists not dates
**Misapplication:** Calendar with too few events (looks empty); no list view alternative; poor mobile adaptation of calendar grid
**UX Laws:** Chunking (time buckets), Mental Model (maps to physical calendar)

### Preview
**Use when:** Users want to see the result before committing; content creation or editing; formatting changes
**Don't use when:** Action is trivial to undo; preview adds significant latency
**Misapplication:** Preview that doesn't match the final output; preview requires extra navigation
**Also called:** Live Preview, WYSIWYG
**UX Laws:** H5 (Error Prevention), User Control (H3)

### FAQ
**Use when:** Common questions exist and are well-known; users need quick answers; support volume needs reduction
**Don't use when:** Questions aren't actually frequent (use searchable help); content is complex (use documentation)
**Misapplication:** Too many questions (>20 without categorization); outdated answers; no search function
**UX Laws:** Recognition over Recall (H6), H10 (Help and Documentation)

---

## Feedback Patterns

### Notifications
**Use when:** Time-sensitive or contextually relevant information; action required
**Don't use when:** Non-urgent information; marketing (users learn to ignore)
**Misapplication:** Too frequent (notification fatigue); no way to manage preferences; mixing urgent and non-urgent
**UX Laws:** Selective Attention (compete for limited attention), Von Restorff (should stand out)

### Modal
**Use when:** User confirmation required; focused task that shouldn't be interrupted; urgent information
**Don't use when:** Content that doesn't require immediate action; newsletter signups on page load; non-blocking information
**Misapplication:** Modal on page entry (before user has context); content that could be inline; no close button; can't dismiss with Escape
**UX Laws:** User Control (H3 — must be closable), Selective Attention (forces focus)

### Inline Hints / Coachmarks
**Use when:** First-time feature discovery; complex features; progressive onboarding
**Don't use when:** Obvious functionality; every feature (tooltip fatigue)
**Misapplication:** Showing all tips at once (tour fatigue); can't dismiss; blocks interaction with the thing it's explaining
**UX Laws:** Paradox of Active User (users skip instructions), Recognition over Recall (H6)

### Guided Tour / Walkthrough
**Use when:** First-time use of a complex product; introducing new features; onboarding flow
**Don't use when:** Interface is self-explanatory; users are returning (should be dismissible); mobile with limited screen space
**Misapplication:** Forced tours with no skip option; showing everything at once instead of progressive steps; tours that don't match actual UI state
**Also called:** Intro Tour, Joyride
**UX Laws:** Paradox of Active User (users want to act, not read), Selective Attention

### Playthrough
**Use when:** Users need to learn by doing; complex workflows; high-stakes tasks where practice matters
**Don't use when:** Tasks are self-explanatory; users are already experienced; no safe sandbox available
**Misapplication:** Playthrough that doesn't match real experience; no way to skip for experienced users
**Also called:** Interactive Tutorial, Sandbox
**UX Laws:** Learning by doing is more effective than reading

### Undo vs. Confirm
**Undo — Use when:** Action is reversible; fast recovery is important; action is frequent
**Confirm — Use when:** Action is irreversible; consequences are significant; action is infrequent
**Misapplication:** Confirm dialogs for reversible actions (slows users down); no undo for destructive actions
**UX Laws:** User Control (H3), Error Prevention (H5)

### Autosave
**Use when:** Data loss would be significant; users work in long sessions; content creation or editing
**Don't use when:** Users expect explicit save (e.g., publishing); saving has side effects visible to others
**Misapplication:** No indication that save occurred; autosave that publishes drafts; no version history for recovery
**UX Laws:** Error Prevention (H5), H1 (Visibility — show save status)

### Morphing Controls
**Use when:** A control's available actions change based on context/state; reducing UI clutter
**Don't use when:** Users need to see all available actions at once; state changes are confusing
**Misapplication:** Controls that morph without clear visual feedback; user doesn't understand why options changed
**UX Laws:** H1 (Visibility of System Status), Progressive Disclosure

---

## Social and Engagement Patterns

### Activity Stream
**Use when:** Users need to track what's happening in their network/workspace
**Don't use when:** Activity is sparse; items aren't time-sensitive
**Misapplication:** Mixing critical and trivial updates; no filtering; no grouping
**UX Laws:** Serial Position Effect (recent items get more attention)

### Favorites / Bookmarks
**Use when:** Users frequently return to specific items; large catalogs where search alone isn't enough
**Don't use when:** Few items to track; system already surfaces recently used
**UX Laws:** Recognition over Recall (H6 — saves re-finding)

### Completeness Meter / Progress Bar
**Use when:** Profile setup, onboarding, multi-step processes, showing mastery
**Don't use when:** Completion isn't meaningful; linear tasks (use steps left instead)
**Misapplication:** Starting at 0% (give a head start); never reaching 100% (demotivating)
**UX Laws:** Goal-Gradient Effect, Zeigarnik Effect

### Chat / Messaging
**Use when:** Real-time communication between users; support interactions; collaborative workflows
**Don't use when:** Asynchronous communication is sufficient (use comments); conversation isn't central to the task
**Misapplication:** Chat that loses context when window closes; no message status (sent, delivered, read); no way to search history
**Also called:** Direct Messaging, Group Chat
**UX Laws:** Doherty Threshold (immediate feedback), H1 (Visibility of message status)

### Follow vs. Friend
**Follow (asymmetric):** One user subscribes to another's updates without mutual agreement. Use for content creators, public figures, interest-based connections
**Friend (symmetric):** Mutual connection requires both parties to agree. Use for personal networks, trust-based sharing
**Misapplication:** Using symmetric friending when asymmetric following is more appropriate (content platforms); no way to control what you see from connections
**UX Laws:** Social norms (market vs. social), User Control (H3)

### Reactions / Rating
**Use when:** Users need lightweight ways to express sentiment; content quality needs crowd-sourcing
**Don't use when:** Detailed feedback is needed (use comments); ratings are easily gamed
**Misapplication:** Too many reaction options (decision paralysis); no clear meaning for each reaction; ratings without context (what's being rated?)
**UX Laws:** Hick's Law (limit options), Social Proof

### Collectible Achievements
**Use when:** Motivating specific behaviors; onboarding completion; community engagement
**Don't use when:** Task is its own reward; achievements feel patronizing for the audience; gamification distracts from primary goals
**Misapplication:** Too many trivial achievements (devalues them); achievements that encourage bad behavior; no clear progress toward achievements
**Also called:** Badges, Trophies
**UX Laws:** Goal-Gradient Effect, Zeigarnik Effect, Variable Reward

### Leaderboard
**Use when:** Healthy competition motivates the audience; relative ranking matters; community engagement
**Don't use when:** Competition is demotivating (most contexts); users are far from the top (discouraging); rankings reveal sensitive data
**Misapplication:** Showing global leaderboard (intimidating) instead of local/friends; no way to opt out; rewarding quantity over quality
**UX Laws:** Social Proof, Goal-Gradient Effect

### Testimonials
**Use when:** Building trust for purchase decisions; social proof is needed; new users evaluating the product
**Don't use when:** Audience is already committed; testimonials feel inauthentic; B2B with specific technical requirements
**Misapplication:** Generic praise without specifics; no attribution or photos (feels fake); testimonials that don't address user concerns
**UX Laws:** Social Proof, Aesthetic-Usability Effect

### Invite Friends
**Use when:** Product has network effects; existing users can vouch for the experience; organic growth is a goal
**Don't use when:** Product doesn't benefit from more users; invitation feels spammy; onboarding can't handle rapid growth
**Misapplication:** Requesting access to entire contact list; sending invites without explicit user consent; no incentive alignment
**UX Laws:** Social norms, User Control (H3)

---

## Data Interaction Patterns

### Drag & Drop
**Use when:** Spatial arrangement matters; reordering lists; moving items between containers; creative tools
**Don't use when:** Target area is small; mobile-first (gestures conflict); accessibility is critical (always provide keyboard alternative)
**Misapplication:** No visual feedback during drag; no keyboard alternative; unclear drop targets; losing data on failed drop
**UX Laws:** Direct Manipulation, Fitts's Law (target size matters), H1 (Visibility during drag)

### Keyboard Shortcuts
**Use when:** Daily-use applications; power users need efficiency; repetitive actions
**Don't use when:** Casual/infrequent use; shortcuts conflict with OS defaults; mobile platforms
**Misapplication:** No discoverability path (users don't know shortcuts exist); non-standard key combos; no way to see all shortcuts
**Also called:** Hotkeys, Accelerators
**UX Laws:** H7 (Flexibility and Efficiency), perpetual intermediates want these

### Paywall
**Use when:** Premium content has clear value; free tier demonstrates enough value to convert; sustainable business model requires it
**Don't use when:** Users can easily find the content elsewhere for free; paywall appears before any value is demonstrated
**Misapplication:** Hard paywall with no free content (no way to evaluate); soft paywall that's too generous (no conversion pressure); unclear what's behind the wall
**UX Laws:** Peak-End Rule, Goal-Gradient Effect (show what they're missing)

---

## Pattern Anti-Patterns

Patterns used in ways that harm the user experience:

| Anti-Pattern | What Happens | Root Cause |
|---|---|---|
| **Dark pattern modal** | Pop-up on entry begging for newsletter signup | Business goal overrides user need |
| **Confirm-shaming** | "No thanks, I don't like saving money" as dismiss option | Manipulative copy |
| **Hidden unsubscribe** | 12 clicks to cancel a subscription | Intentional friction |
| **Roach motel** | Easy to sign up, impossible to delete account | Asymmetric ease |
| **Forced continuity** | Free trial auto-converts to paid with no warning | Missing transparency |
| **Trick question** | Double negatives or pre-checked boxes in opt-outs | Exploiting cognitive load |
| **Bait and switch** | Advertised feature requires upgrade | Misleading expectation |
| **Sneak into basket** | Extra items added to cart during checkout | Exploiting inattention |
| **Privacy zuckering** | Confusing settings that expose more data than intended | Deliberate complexity |
| **Misdirection** | Visual design draws attention away from important information | Strategic visual hierarchy abuse |

**Principle:** Patterns should serve the user's goal. If a pattern primarily serves the business at the user's expense, it's a dark pattern — flag it.

---

## Pattern Selection Guide

When choosing a pattern, consider:

| Decision Factor | Questions to Ask |
|---|---|
| **User expertise** | Are users beginners, intermediates, or experts? Beginners need guided patterns (wizards, coachmarks). Experts need efficient ones (keyboard shortcuts, inline editing) |
| **Frequency of use** | Daily-use features → optimize for speed (shortcuts, autosave). Rare features → optimize for learnability (guided tours, progressive disclosure) |
| **Task complexity** | Simple task → single pattern. Complex task → combine patterns (wizard + preview + autosave) |
| **Data volume** | Few items → simple list. Many items → search + filter + pagination. Massive dataset → faceted search + autocomplete |
| **Error cost** | Low cost → undo. High cost → confirm + preview. Irreversible → confirm + explicit input ("type DELETE to confirm") |
| **Platform** | Desktop → richer patterns (drag & drop, keyboard shortcuts). Mobile → simpler patterns (swipe, tap). Touch → larger targets (44×44px minimum) |
