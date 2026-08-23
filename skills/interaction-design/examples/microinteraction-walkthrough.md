# Microinteraction Walkthrough

Designing a "Favorite" toggle interaction end-to-end using the four-part framework.

---

## Context

**Product:** A recipe-sharing web and mobile app
**Feature:** Users can favorite recipes to save them to a personal collection
**Interaction:** Tapping a heart icon on a recipe card toggles the favorite state

---

## Step 1: Define the Goal

**User goal:** Save a recipe I like so I can find it later.

This is a binary state toggle — on or off — which makes it a single microinteraction, not a feature.

---

## Step 2: Design the Trigger

### Type
Manual trigger — user taps/clicks a heart icon.

### Placement
On the recipe card (top-right corner) AND on the recipe detail page (next to the title). Same trigger, same behavior, two locations.

### Data Brought Forward
- **Not favorited:** Empty heart outline
- **Favorited:** Filled heart in accent color
- **Favorited count:** "24 saves" text below heart on detail page (social proof)

The user can see the favorite state without tapping — the filled vs. outline heart communicates status immediately.

### Trigger States

| State | Recipe Card | Detail Page |
|-------|-----------|-------------|
| **Default (not favorited)** | Outline heart, `color-text-tertiary` | Outline heart, `color-text-secondary`, "Save" label |
| **Default (favorited)** | Filled heart, `color-feedback-error` (red) | Filled heart, `color-feedback-error`, "Saved" label |
| **Hover** | Scale to 110%, outline thickens | Scale to 105%, background tint |
| **Active/Pressed** | Scale to 90% (squash) | Scale to 95% |
| **Disabled** | 40% opacity (e.g., user not logged in) | 40% opacity + "Log in to save" tooltip |
| **Loading** | Pulse animation on heart | Pulse animation |

---

## Step 3: Design the Rules

### Primary Action
- Tap unfavorited → Favorite the recipe (add to user's collection)
- Tap favorited → Unfavorite the recipe (remove from collection)

### Sequence (Favorite)
1. Heart immediately fills (optimistic UI — don't wait for server)
2. API request sent to save the favorite
3. If success: count increments, state is persisted
4. If failure: heart reverts to outline, brief error toast

### Sequence (Unfavorite)
1. Heart immediately empties (optimistic UI)
2. API request sent to remove the favorite
3. If success: count decrements
4. If failure: heart reverts to filled, brief error toast

### Smart Defaults
- If user is not logged in: show heart as disabled. On tap, prompt login (not a full redirect — a sheet/modal). After login, complete the favorite action automatically
- Count is fetched with the recipe data. No extra request

### Edge Cases

| Edge Case | Handling |
|-----------|---------|
| Rapid double-tap | Debounce. Only send the final state after 300ms of no taps. Visual state toggles immediately for each tap |
| Network failure | Revert visual state. Show toast: "Couldn't save. Try again." Heart returns to previous state |
| Already favorited on another device | Sync state on load. No conflict — last-write-wins is fine for favorites |
| Recipe deleted while favorited | Remove from favorites list on next load. No error needed |
| User taps from notification | Deep-link to recipe detail. Favorite state is correct on load |

### What the System Remembers
- Favorite state per recipe per user (persistent, server-side)
- Total favorite count per recipe (cached, eventually consistent)

---

## Step 4: Design the Feedback

### Visual Feedback

**Favoriting (outline → filled):**
1. Heart scales down to 90% (50ms, ease-in) — the "squash"
2. Heart fills with red while scaling up to 120% (150ms, spring) — the "pop"
3. Heart settles to 100% (100ms, ease-out) — landing
4. Brief particle burst around heart (3-5 small hearts or sparkles, 300ms, fade out) — delight

**Total timing:** ~400ms

**Unfavoriting (filled → outline):**
1. Heart scales down to 95% (50ms, ease-in)
2. Fill drains (crossfade to outline, 100ms)
3. Heart returns to 100% (50ms, ease-out)

**Total timing:** ~200ms — unfavoriting is faster and less celebratory. Exit is swift.

### Haptic Feedback (Mobile)
- **Favoriting:** Medium impact tap at the pop moment (step 2)
- **Unfavoriting:** Light tap at the drain moment (step 2)

### Auditory Feedback
None. Favoriting is a frequent, casual action. Sound would become annoying. (Exception: if the product has an explicitly playful brand, a subtle "pop" sound could work — but it must be mutable.)

### Error Feedback
- Toast appears at bottom: "Couldn't save favorite. Try again." with a retry button
- Toast auto-dismisses after 5 seconds
- Heart reverts to previous state with a 150ms crossfade (no jarring snap)

---

## Step 5: Design Loops and Modes

### Modes
**None.** This interaction has no modes. Tapping always toggles. No settings to configure.

### Loops
- **No retry loop:** If the API call fails, the system does not auto-retry. It reverts the visual state and shows the error toast. The user can tap again to retry manually
- **Debounce loop:** Rapid taps are debounced to 300ms. The visual state toggles immediately (responsive), but the API call only fires once with the final state

### Long Loop (The Long Wow)

| Phase | Behavior |
|-------|---------|
| **First favorite** | After the animation completes, show a brief tooltip: "Find your saved recipes in Favorites." This teaches the user where to access favorites. Show only once |
| **Regular use** | Standard animation. No tooltip. Fast and quiet |
| **After 10+ favorites** | On the Favorites page, surface a suggestion: "You've saved 15 desserts. Browse our Dessert collection?" — the system recognizes patterns |
| **Return after absence** | "Welcome back! You have 23 saved recipes." — reconnect the user to their collection |

---

## Step 6: State Machine

```
[Unfavorited] --tap--> [Saving]
[Saving] --API success--> [Favorited]
[Saving] --API failure--> [Unfavorited] + show error toast

[Favorited] --tap--> [Removing]
[Removing] --API success--> [Unfavorited]
[Removing] --API failure--> [Favorited] + show error toast

[Unfavorited] --tap (not logged in)--> [Login Prompt]
[Login Prompt] --login success--> [Saving]
[Login Prompt] --dismiss--> [Unfavorited]
```

Note: Visual state changes optimistically (immediately on tap), but the actual state machine waits for API confirmation before settling.

---

## Step 7: Accessibility

| Requirement | Implementation |
|-------------|---------------|
| **Keyboard** | Focus with Tab. Toggle with Enter or Space |
| **Focus ring** | 2px ring around heart icon, `color-border-focus`, 2px offset |
| **ARIA** | `role="checkbox"`, `aria-checked="true/false"`, `aria-label="Save [Recipe Name] to favorites"` |
| **Screen reader** | On toggle: announces "Saved to favorites" or "Removed from favorites" via `aria-live="polite"` region |
| **Color independence** | State communicated by fill (filled vs. outline) and label ("Save" vs. "Saved"), not just color |
| **Reduced motion** | Skip scale animation and particle burst. Instant crossfade between filled/outline (50ms opacity transition only) |
| **Touch target** | 44×44px minimum hit area (heart icon may be visually smaller, but tap target extends) |

---

## Outcome

This single microinteraction — a heart toggle — touches all four parts of the framework:

- **Trigger:** Heart icon with data forward (filled/outline state), clear states
- **Rules:** Optimistic UI, debounce, login handling, error recovery
- **Feedback:** Asymmetric animation (celebratory favorite, swift unfavorite), haptic, contextual errors
- **Loops/Modes:** No modes (good). Long loop with first-use education and pattern recognition

Total specification: ~2 pages. Implementation: ~1 day. Impact: the difference between a product users tolerate and one they love.
