# Accessibility Audit Walkthrough

This example walks through auditing a fictional e-commerce checkout page for "GreenLeaf," an organic grocery delivery service. We'll run the 5-layer audit process and produce prioritized findings.

---

## Context

**Page:** GreenLeaf checkout (cart → shipping → payment → confirmation)
**Target:** WCAG 2.2 Level AA
**Tools:** axe DevTools, VoiceOver (macOS), Chrome DevTools
**Date:** March 2026

---

## Layer 1: Automated Scan (axe DevTools)

Running axe DevTools on the checkout page returns:

| # | Issue | WCAG | Impact | Elements |
|---|---|---|---|---|
| 1 | Color contrast insufficient | 1.4.3 | Serious | 7 elements (subtotal labels, help text, placeholder text) |
| 2 | Form elements do not have associated labels | 1.3.1 | Critical | 3 elements (card number, expiry, CVV) |
| 3 | Images do not have alt attributes | 1.1.1 | Critical | 2 elements (product thumbnails in cart) |
| 4 | Links do not have discernible text | 2.4.4 | Serious | 1 element (social login icon) |
| 5 | Document does not have a main landmark | 1.3.1 | Moderate | Page |
| 6 | Page does not contain a level-one heading | 1.3.1 | Moderate | Page |

**Lighthouse accessibility score:** 62/100

---

## Layer 2: Keyboard Navigation

| Step | Result | Issue? |
|---|---|---|
| Tab from page top | Focus starts at logo link | OK |
| Skip link? | No skip link present | **Issue: Missing skip link** |
| Tab through header nav | 8 nav links, all reachable | OK |
| Tab to cart items | Can reach "Remove" buttons | OK |
| Tab to quantity fields | Focus visible but low contrast | **Issue: Low-contrast focus ring** |
| Tab to promo code field | Reachable | OK |
| Tab to shipping form | Address fields reachable | OK |
| Tab to payment fields | Card fields inside iframe, focus works | OK |
| Tab to "Place Order" button | Reachable, Enter activates | OK |
| Tab past "Place Order" | Focus goes to footer, logical | OK |
| Open "Edit address" modal | Focus does NOT move to modal | **Issue: Focus not managed on modal open** |
| Tab inside modal | Focus escapes to page behind modal | **Issue: Focus not trapped in modal** |
| Press Escape in modal | Nothing happens | **Issue: Modal doesn't close on Escape** |
| Close modal via X button | Focus does not return to trigger | **Issue: Focus not restored on close** |

---

## Layer 3: Screen Reader Testing (VoiceOver)

| Check | Result | Issue? |
|---|---|---|
| Headings (Rotor) | No h1 found. Section headings are styled `<div>`s, not `<h2>`s | **Issue: No semantic headings** |
| Landmarks (Rotor) | `<nav>` present, no `<main>`, no `<footer>` | **Issue: Missing landmarks** |
| Cart product images | "Image" announced with no description | **Confirmed: Missing alt text** |
| Quantity input | "Stepper" — no label announced | **Issue: Unlabeled quantity input** |
| "Remove" button | "Button: Remove" — which item? Ambiguous | **Issue: Ambiguous button label** |
| Shipping address fields | Labels announced correctly | OK |
| Payment card fields | "Edit text" — no label announced | **Confirmed: Missing card field labels** |
| "Place Order" button | "Button: Place Order" | OK |
| Order summary prices | Read correctly | OK |
| Error on empty required field | Red border appears, no announcement | **Issue: Errors not announced** |
| Promo code success message | "Promo applied" toast appears visually, not announced | **Issue: Status message not announced** |

---

## Layer 4: Visual Review

| Check | Result | Issue? |
|---|---|---|
| Text contrast (body text) | #333 on #fff = 12.6:1 | OK |
| Text contrast (help text) | #aaa on #fff = 2.3:1 | **Confirmed: Fails 4.5:1** |
| Text contrast (placeholder) | #ccc on #fff = 1.6:1 | **Confirmed: Fails 4.5:1** |
| Subtotal labels | #888 on #f5f5f5 = 3.5:1 | **Fails 4.5:1 for normal text** |
| Focus indicator | 1px light blue outline on white background | **Issue: Low contrast focus ring (~2:1)** |
| Color as sole indicator | Error fields: red border only, no icon or text | **Issue: Color-only error indication** |
| Touch targets (mobile) | "Remove" links are 12×16px | **Issue: Fails 24×24px minimum** |
| 200% zoom | Layout reflows, some overlap in payment section | **Issue: Overlap at 200% zoom** |
| 320px reflow | Cart table requires horizontal scroll | OK (tables exempt) |
| Text spacing test | Promo code button text gets clipped | **Issue: Text clipped with increased spacing** |

---

## Layer 5: Flow Testing

| Check | Result | Issue? |
|---|---|---|
| Complete checkout (keyboard only) | Possible but modal issues block address editing | **Blocked by modal issues** |
| Form errors (submit empty) | Red borders appear, no error summary, no field-level messages | **Issue: Inadequate error handling** |
| Authentication | Guest checkout available, no CAPTCHA | OK |
| Help location | Help link in footer, consistent with other pages | OK |
| Redundant entry | Billing address defaults to shipping (can uncheck) | OK |

---

## Compiled Findings

### Finding 1: Payment Card Fields Missing Labels

**Severity:** Critical
**WCAG:** 1.3.1 (A), 1.1.1 (A)
**Affects:** Screen reader users — cannot determine which field is for card number, expiry, or CVV

**Current:**
```html
<input type="text" class="card-number" placeholder="Card number">
<input type="text" class="expiry" placeholder="MM/YY">
<input type="text" class="cvv" placeholder="CVV">
```

**Fix:**
```html
<label for="card-number">Card number</label>
<input type="text" id="card-number" autocomplete="cc-number" inputmode="numeric">

<label for="card-expiry">Expiration date (MM/YY)</label>
<input type="text" id="card-expiry" autocomplete="cc-exp">

<label for="card-cvv">Security code (CVV)</label>
<input type="text" id="card-cvv" autocomplete="cc-csc" inputmode="numeric">
```

**Effort:** Small

---

### Finding 2: Edit Address Modal Not Accessible

**Severity:** Critical
**WCAG:** 2.1.2 (A), 2.4.3 (A), 4.1.2 (A)
**Affects:** Keyboard users — cannot use the modal properly; may get trapped or lose their place

**Issues:**
- Focus doesn't move to modal on open
- Focus isn't trapped within modal
- Escape doesn't close modal
- Focus doesn't return to trigger on close
- Modal not announced as dialog

**Fix:**
```html
<dialog id="edit-address" aria-labelledby="modal-title">
  <h2 id="modal-title">Edit shipping address</h2>
  <!-- form fields -->
  <button>Save</button>
  <button>Cancel</button>
</dialog>
```

Using the native `<dialog>` element with `showModal()` handles focus trapping, Escape, and backdrop automatically. If using a custom implementation, all four focus behaviors must be manually coded.

**Effort:** Medium

---

### Finding 3: Low Contrast Text Throughout

**Severity:** High
**WCAG:** 1.4.3 (AA)
**Affects:** Low vision users, users in bright environments — 7 elements fail minimum contrast

| Element | Current | Ratio | Required | Fix |
|---|---|---|---|---|
| Help text | #aaa on #fff | 2.3:1 | 4.5:1 | Change to #595959 |
| Placeholder text | #ccc on #fff | 1.6:1 | 4.5:1 | Change to #767676 |
| Subtotal labels | #888 on #f5f5f5 | 3.5:1 | 4.5:1 | Change to #595959 or darken bg |

**Effort:** Small

---

### Finding 4: No Semantic Structure

**Severity:** High
**WCAG:** 1.3.1 (A)
**Affects:** Screen reader users — cannot navigate by headings or landmarks

**Issues:**
- No `<h1>` on the page
- Section titles ("Your Cart," "Shipping," "Payment") are `<div>`s, not headings
- No `<main>` landmark
- No `<footer>` landmark

**Fix:**
```html
<main>
  <h1>Checkout</h1>
  <section aria-labelledby="cart-heading">
    <h2 id="cart-heading">Your Cart</h2>
    <!-- cart items -->
  </section>
  <section aria-labelledby="shipping-heading">
    <h2 id="shipping-heading">Shipping</h2>
    <!-- shipping form -->
  </section>
  <section aria-labelledby="payment-heading">
    <h2 id="payment-heading">Payment</h2>
    <!-- payment form -->
  </section>
</main>
```

**Effort:** Small

---

### Finding 5: Form Errors Not Accessible

**Severity:** High
**WCAG:** 3.3.1 (A), 3.3.3 (AA)
**Affects:** Screen reader users — errors not announced; all users — no guidance on how to fix

**Current behavior:** Red border on invalid fields, no text message, no announcement.

**Fix:**
```html
<!-- Error summary at top of form -->
<div role="alert" aria-labelledby="error-heading">
  <h3 id="error-heading">Please fix 2 errors:</h3>
  <ul>
    <li><a href="#card-number">Card number is required</a></li>
    <li><a href="#card-expiry">Enter a valid expiration date (MM/YY)</a></li>
  </ul>
</div>

<!-- Per-field error -->
<label for="card-number">Card number</label>
<input type="text" id="card-number" aria-invalid="true" aria-describedby="card-error">
<span id="card-error" class="error">Card number is required</span>
```

**Effort:** Medium

---

### Finding 6: Missing Product Image Alt Text

**Severity:** Moderate
**WCAG:** 1.1.1 (A)
**Affects:** Screen reader users — can't identify items in cart

**Fix:** `<img src="tomatoes.jpg" alt="Organic vine tomatoes, 1 lb">`

**Effort:** Small

---

### Finding 7: Ambiguous "Remove" Buttons

**Severity:** Moderate
**WCAG:** 2.4.4 (A)
**Affects:** Screen reader users — all buttons say "Remove" with no context

**Fix:** `<button aria-label="Remove Organic vine tomatoes from cart">Remove</button>`

**Effort:** Small

---

## Prioritized Remediation Plan

| # | Finding | WCAG | Severity | Effort | Tier |
|---|---|---|---|---|---|
| 1 | Payment fields missing labels | 1.3.1 (A) | Critical | Small | 1 |
| 2 | Modal not accessible | 2.1.2 (A) | Critical | Medium | 1 |
| 3 | Low contrast text | 1.4.3 (AA) | High | Small | 1 |
| 4 | No semantic structure | 1.3.1 (A) | High | Small | 1 |
| 5 | Errors not accessible | 3.3.1 (A) | High | Medium | 1 |
| 6 | Missing image alt text | 1.1.1 (A) | Moderate | Small | 2 |
| 7 | Ambiguous button labels | 2.4.4 (A) | Moderate | Small | 2 |
| 8 | Missing skip link | 2.4.1 (A) | Moderate | Small | 2 |
| 9 | Low contrast focus ring | 2.4.7 (AA) | Moderate | Small | 2 |
| 10 | Small touch targets | 2.5.8 (AA) | Moderate | Small | 2 |
| 11 | Status messages not announced | 4.1.3 (AA) | Moderate | Small | 2 |
| 12 | Color-only error indication | 1.4.1 (A) | Moderate | Small | 2 |
| 13 | Text clipped with spacing | 1.4.12 (AA) | Low | Small | 3 |
| 14 | Overlap at 200% zoom | 1.4.4 (AA) | Low | Medium | 3 |

**Estimated remediation time:** Tier 1 fixes: ~2 days. Tier 2: ~1 day. Tier 3: ~0.5 day.

---

## What This Audit Demonstrated

1. **5-layer approach catches what single-method testing misses** — Automated found 6 issues; the full audit found 14
2. **Automated tools are necessary but not sufficient** — axe missed the modal issues, ambiguous labels, error handling, and focus management problems
3. **Keyboard testing reveals interaction failures** — The modal issues are critical blockers that only Tab testing exposed
4. **Screen reader testing reveals content failures** — Missing headings and ambiguous labels only surface when you hear the page announced
5. **Every finding has a specific code fix** — Not "improve accessibility," but "add `<label for='card-number'>` to the card number input"
