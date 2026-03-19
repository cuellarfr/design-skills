# Common Design Problems: Pattern Recognition Guide

A visual diagnosis guide. When you see these symptoms, here's what's wrong and how to fix it.

---

## Problem 1: The Overwhelming Dashboard

### Symptoms
- 10+ KPI cards all the same size
- Multiple charts competing for attention
- User says "I don't know where to look first"
- High time-to-insight in analytics

### Root Cause
Every metric treated as equally important. No visual hierarchy applied to data.

### Diagnosis
- **Violated:** Hick's Law (too many choices), Visual Hierarchy, Miller's Law
- **What's happening:** Designer included every metric stakeholders requested without prioritizing

### Fix
1. Ask: "Which 3 metrics would this user check every single day?"
2. Make those 3 dramatically larger/more prominent
3. Move remaining metrics to a secondary section or "More metrics" expandable area
4. Add comparison context to each metric (vs. previous period, vs. target)
5. Consider allowing user customization of which metrics appear

### Before/After Mental Model

**Before:** 12 equal boxes → user scans all 12 every time → slow, overwhelming
**After:** 3 hero metrics + "View all" → user scans 3 → fast, focused, with depth available

---

## Problem 2: The Form That Kills Conversion

### Symptoms
- 15+ fields on one page
- No progress indicator
- High abandonment rate at form step
- Required fields unclear until submission

### Root Cause
All data collected at once. No consideration for user effort or progressive disclosure.

### Diagnosis
- **Violated:** Tesler's Law (user bears too much complexity), Cognitive Load, Goal-Gradient Effect
- **What's happening:** Business wants maximum data; design didn't push back on what's actually needed

### Fix
1. **Audit every field:** For each, ask "Do we need this to complete the task, or is it nice-to-have?"
2. **Split into steps:** Group related fields into 3-5 logical steps with progress indicator
3. **Defer optional fields:** Ask for nice-to-haves after the primary task is complete
4. **Use smart defaults:** Pre-fill anything inferable (country from locale, date = today)
5. **Inline validation:** Validate as users go, not all at the end

### Metric to Track
**Before:** Form completion rate. **After:** Expect 25-40% improvement by reducing fields and adding steps.

---

## Problem 3: The Mystery Navigation

### Symptoms
- Icons without text labels
- Hamburger menu hiding primary navigation
- User says "I didn't know that existed"
- Low feature adoption despite feature being available

### Root Cause
Visual minimalism prioritized over discoverability. Designer optimized for aesthetics, not wayfinding.

### Diagnosis
- **Violated:** H6 (Recognition over Recall), Jakob's Law, Selective Attention
- **What's happening:** Icon-only nav requires recall (memorization); hidden nav requires discovery

### Fix
1. **Add text labels to icons** — Research consistently shows icon+label outperforms icon-only
2. **Show primary navigation persistently** — Don't hide the top 5-7 navigation items
3. **Use a collapsible sidebar** — Collapsed = icons + labels on hover. Expanded = icons + labels always
4. **Test with 5 users:** Show them the nav and ask them to find [feature]. If 3+ fail, the nav needs work

### Decision Framework
- **Always visible:** If used daily by most users → persistent nav with icon + label
- **Collapsible:** If screen real estate is tight → icon-only with expand to labeled
- **Hidden (hamburger):** Only for secondary/infrequent actions — never hide primary tasks

---

## Problem 4: The Error Dead End

### Symptoms
- Error message says "Invalid input" or "Error 500"
- User stares at error, unsure what to do
- Support tickets about "the error screen"
- User retries the same action with same result

### Root Cause
Error handling designed for developers, not users.

### Diagnosis
- **Violated:** H9 (Error Recovery), H2 (Match Real World)
- **What's happening:** System error messages exposed directly; no user-friendly translation

### Fix — The 4-Part Error Message

1. **What happened:** "We couldn't process your payment"
2. **Why (if helpful):** "Your card was declined"
3. **How to fix it:** "Please check your card details or try a different payment method"
4. **One-click recovery:** [Try Again] button or [Use Different Card] link

### Error Quality Checklist
- [ ] Written in plain language (no codes, no jargon)
- [ ] Identifies which specific field has the problem
- [ ] Explains what's expected
- [ ] Provides a way to fix it immediately
- [ ] Announced to screen readers

---

## Problem 5: The Feature-Stuffed Interface

### Symptoms
- Every feature visible at all times
- Toolbar with 20+ icons
- Users use only 3-4 features regularly
- New users overwhelmed; power users fine

### Root Cause
Every feature given equal UI prominence. Pareto principle ignored (80% of users use 20% of features).

### Diagnosis
- **Violated:** H8 (Minimalist Design), Pareto Principle, Progressive Disclosure
- **What's happening:** Product grew over time; features were added but never reorganized

### Fix
1. **Analyze usage data:** Which features do 80% of users actually use?
2. **Promote the top 20%:** Make these immediately visible and accessible
3. **Progressively disclose the rest:** "More tools" menu, "Advanced" section, or contextual appearance
4. **Consider role-based views:** Show different defaults for different user types
5. **Offer customization:** Let power users pin their most-used features

### Progressive Disclosure Levels
- **Level 1 (always visible):** The 3-5 actions used by nearly everyone
- **Level 2 (one click away):** The next 5-10 used regularly by many
- **Level 3 (two clicks):** Advanced features used by experts
- **Level 4 (settings/config):** Rarely changed options

---

## Problem 6: The Inconsistent Interface

### Symptoms
- Same action has different names on different pages
- Buttons look different in different sections
- Users report "it feels like different products"
- New team members produce inconsistent UI

### Root Cause
No design system, or design system exists but isn't enforced. Multiple designers working independently.

### Diagnosis
- **Violated:** H4 (Consistency and Standards), Jakob's Law
- **What's happening:** Each page/feature designed in isolation without shared components

### Fix
1. **Audit visual inconsistencies:** Screenshot every button, form, card, and navigation element. Catalog variations
2. **Create a terminology guide:** One word per concept. "Delete" everywhere, not "Delete" / "Remove" / "Trash"
3. **Build a component library:** Shared components used by all designers/developers
4. **Enforce through code:** Use a component library (React components, design tokens) that makes consistency the default
5. **Regular audits:** Quarterly visual consistency check

---

## Problem 7: The Never-Ending Scroll

### Symptoms
- Important content below the fold that users never see
- Low engagement with below-fold content
- Users think the page is shorter than it is

### Root Cause
No visual cue that content continues. False floor created by a section that looks like it could be the end of the page.

### Diagnosis
- **Violated:** H1 (Visibility), Selective Attention
- **What's happening:** A full-width section with lots of white space creates a visual "floor" — users don't scroll past it

### Fix
1. **Add scroll cues:** Partial content visible below the fold (a card cut in half, a heading peeking up)
2. **Avoid false floors:** Don't let a section with white space span the full viewport height
3. **Use anchor navigation:** Table of contents or sticky nav that shows what's below
4. **Prioritize above-fold content:** If it's important, move it up — don't rely on scrolling

---

## Quick Diagnosis Table

| Symptom | Likely Problem | Primary Heuristic/Law | First Fix |
|---|---|---|---|
| "I don't know where to look" | No visual hierarchy | H8, Visual Hierarchy | Make one thing biggest |
| "I didn't know that was there" | Hidden feature | H6, Recognition | Make it visible |
| "I don't understand these options" | Jargon/internal naming | H2, Mental Model | User-test the labels |
| "I don't know if it worked" | No feedback | H1, Doherty Threshold | Add confirmation state |
| "I can't go back" | No undo/escape | H3, User Control | Add undo, back, cancel |
| "This button doesn't match that button" | Inconsistency | H4, Consistency | Audit and unify |
| "I accidentally deleted it" | No error prevention | H5, Error Prevention | Add confirmation or undo |
| "I can't remember what to type" | Recall required | H6, Working Memory | Show options, provide hints |
| "The error just says 'invalid'" | Bad error messages | H9 | 4-part error message |
| "I'm lost" | Poor navigation | Navigation | Add breadcrumbs, active state, page names |
| "It's too much" | Feature overload | Pareto, Progressive Disclosure | Show top 20%, hide rest |
