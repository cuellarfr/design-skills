# Motion Principles

Animation principles adapted for UI, timing and easing guidelines, motion tokens, reduced motion, and platform motion patterns.

---

## Purpose of Motion in UI

Motion serves four functions. If an animation doesn't serve at least one, remove it.

| Function | When to Use | Duration Range | Priority |
|----------|------------|----------------|----------|
| **Feedback** | Confirming a user action | 100-200ms | Highest — directly responds to input |
| **Orientation** | Showing spatial relationships, navigation | 200-400ms | High — helps users understand where they are |
| **Focus** | Directing attention to changes | 150-300ms | Medium — guides the eye to what matters |
| **Delight** | Brand personality, celebration | 300-600ms | Lowest — earn it sparingly |

---

## 12 Animation Principles Adapted for UI

From Disney's principles (Thomas & Johnston), adapted for digital interfaces:

### 1. Timing
Speed conveys weight and importance. Fast = light, responsive. Slow = heavy, significant.
- **UI rule:** Direct-manipulation feedback under 200ms. Transitions 200-400ms. Never exceed 500ms for functional animation.

### 2. Easing (Slow In/Slow Out)
Nothing in the physical world starts or stops instantly. Motion should accelerate and decelerate.
- **UI rule:** Use ease-out for elements entering (arrive quickly, settle gently). Use ease-in for elements exiting (leave quickly). Use ease-in-out for elements moving on-screen.

### 3. Anticipation
A preparatory movement before the main action.
- **UI rule:** Use sparingly. A brief scale-up (102%) before a button bounce. A slight pull-back before a swipe animation. Overuse feels cartoonish.

### 4. Follow-Through
Elements don't stop dead — they overshoot slightly and settle.
- **UI rule:** Spring physics for playful interfaces. Subtle overshoot (2-5%) for toggle switches, modal appearances. Zero overshoot for data-heavy professional interfaces.

### 5. Staging
Present information so the audience knows where to look.
- **UI rule:** Animate one thing at a time. If multiple elements enter, stagger them (50-100ms delay between each). The most important element animates first.

### 6. Arcs
Natural movement follows curved paths, not straight lines.
- **UI rule:** Elements that move across the screen should follow a slight curve, especially for longer distances. Short movements (button press, toggle) can be linear.

### 7. Secondary Action
Supporting motion that adds richness without distracting.
- **UI rule:** When a card expands, its shadow grows as a secondary action. When a dialog opens, the background dims. These support but don't compete with the primary motion.

### 8. Squash and Stretch
Objects deform to convey weight and elasticity.
- **UI rule:** Very subtle in UI. A loading dot that stretches slightly as it bounces. A notification that squashes slightly on landing. Keep deformation under 10%.

### 9. Exaggeration
Amplify to make an action clear.
- **UI rule:** Error shake is exaggerated (wider displacement than a real head-shake would be). Success checkmark draws with emphasis. Subtle exaggeration makes intent clear.

### 10. Solid Drawing (Consistency)
Objects maintain consistent dimensionality.
- **UI rule:** Elements should maintain consistent proportions during animation. A card that scales up should scale uniformly. Shadows should remain physically plausible.

### 11. Appeal
Animation should be pleasing to watch.
- **UI rule:** Smooth easing curves. No jitter. No jarring speed changes. Motion should feel effortless.

### 12. Straight-Ahead vs. Pose-to-Pose
Either animate continuously or define key poses and interpolate.
- **UI rule:** Most UI animation is pose-to-pose (start state → end state, browser interpolates). Use straight-ahead only for physics simulations (drag, throw, bounce).

---

## Timing Guidelines

### Duration by Interaction Type

| Interaction | Duration | Easing | Notes |
|------------|----------|--------|-------|
| Button press feedback | 50-100ms | ease-out | Fastest. Color change, scale |
| Toggle switch | 150-200ms | ease-in-out | State swap animation |
| Tooltip appear | 100-150ms | ease-out | Quick in, don't delay information |
| Tooltip disappear | 75-100ms | ease-in | Faster exit than enter |
| Dropdown open | 150-200ms | ease-out | Reveals content |
| Dropdown close | 100-150ms | ease-in | Close is faster than open |
| Modal open | 200-300ms | ease-out | Fade + scale from 95% to 100% |
| Modal close | 150-200ms | ease-in | Fade + scale to 95% |
| Page transition | 250-350ms | ease-in-out | Slide, fade, or shared element |
| Skeleton → content | 150-200ms | ease-out | Crossfade. No layout shift |
| Notification enter | 200-300ms | ease-out (or spring) | Slide in + fade |
| Notification exit | 150-200ms | ease-in | Slide out + fade |
| Error shake | 400-600ms | spring | 2-3 oscillations, decreasing |
| Success checkmark | 400-600ms | ease-out | Draw + scale. Celebratory |
| Pull to refresh | Continuous | spring | Follows finger, bounces on release |
| Scroll momentum | Physics-based | deceleration | Matches platform behavior |

### Easing Curves

| Name | CSS Value | Use |
|------|-----------|-----|
| **Standard** | `cubic-bezier(0.2, 0, 0, 1)` | Most transitions. Moving elements on screen |
| **Enter (decelerate)** | `cubic-bezier(0, 0, 0.2, 1)` | Elements appearing, fading in, sliding in |
| **Exit (accelerate)** | `cubic-bezier(0.4, 0, 1, 1)` | Elements leaving, fading out, sliding out |
| **Linear** | `linear` | Opacity fades. Progress bars. Color transitions |
| **Spring** | Varies by framework | Bouncy, playful. Toggles, notifications, celebrations |

### The Rule of Asymmetry

**Enter slower, exit faster.** Arrival is celebrated; departure is swift.

- Modal opens: 250ms. Modal closes: 150ms
- Tooltip appears: 150ms. Tooltip disappears: 100ms
- Sidebar opens: 300ms. Sidebar closes: 200ms

---

## Motion Tokens

Standardize timing across the design system:

```
motion-duration-instant:    0ms      (no animation)
motion-duration-fast:       100ms    (hover, toggle)
motion-duration-normal:     200ms    (open, appear, state change)
motion-duration-slow:       300ms    (page transition, complex reveal)
motion-duration-slower:     400ms    (celebration, complex orchestration)

motion-easing-standard:     cubic-bezier(0.2, 0, 0, 1)
motion-easing-enter:        cubic-bezier(0, 0, 0.2, 1)
motion-easing-exit:         cubic-bezier(0.4, 0, 1, 1)
motion-easing-linear:       linear
```

---

## Reduced Motion

### `prefers-reduced-motion`

Users who set "Reduce motion" in their OS settings have told you they don't want unnecessary animation. Respect it.

**Minimum response (required):**
- Remove all transform-based animations (slide, scale, bounce, rotate)
- Remove parallax effects
- Keep opacity fades (cross-fade is acceptable)
- Instant state changes where animation existed

**Ideal response:**
- Replace motion with instant state changes
- Replace slide-in panels with instant appearance
- Replace animated progress with static progress bars
- Keep functional feedback (loading spinners can remain but should not bounce/pulse)
- Reduce auto-playing media

### Implementation

```css
@media (prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
  }
}
```

Override selectively for truly essential animations (like a loading spinner that needs to spin).

---

## Platform Motion Conventions

### Material Design 3

- **Container transforms**: Shared-element transitions between screens. A card expands into a detail page, maintaining spatial continuity
- **Fade through**: For unrelated transitions. Element fades out, new element fades in. 300ms total (150 out + 150 in)
- **Shared axis**: For related transitions (wizard steps, tabs). Content slides along the shared axis of navigation

### Apple HIG

- **Fluid transitions**: Elements morph between states rather than cutting. Navigation push/pop uses edge-to-edge slide
- **Spring animations**: iOS uses spring physics for many interactions (sheet pull-down, notification bounce). Damping ~0.7, stiffness varies
- **Contextual**: Transitions reflect the spatial relationship between the trigger and the destination
