# Accessibility Rules File (for AI Coding Agents)

A drop-in constraints block that teaches an AI coding agent to generate accessible UI **by default**, instead of producing visually-correct-but-semantically-broken markup.

**Why this exists:** General-purpose code models produce inaccessible UI by default — they model what code *looks like*, not what it *means*. CSS can make a `<div>` *look* like a button; only HTML semantics make it *be* one. This file closes that gap at generation time, which costs ~3–8 minutes per component versus ~45–90 minutes of post-hoc remediation.

## Where to put it

Paste the block below into whichever file your agent reads as standing instructions:

| Agent / Tool | File |
|---|---|
| Claude Code | `CLAUDE.md` (project root or `.claude/`) |
| Cursor | `.cursor/rules/accessibility.mdc` (or legacy `.cursorrules`) |
| GitHub Copilot | `.github/copilot-instructions.md` |
| Codex / AGENTS.md-based agents | `AGENTS.md` |
| Windsurf | `.windsurfrules` |
| Zed | `.rules` |

Keep it in version control so every contributor's agent inherits the same constraints. Trim any sections that don't apply to your stack (e.g., drop the React-library guidance for a Vue project).

---

## The rules block (copy from here)

```markdown
## Accessibility requirements (non-negotiable)

Generate UI that conforms to WCAG 2.2 AA. These are hard constraints, not
suggestions. When a requirement conflicts with brevity, choose accessibility.

### HTML semantics — use the right element first
- Actions use `<button type="button">`. NEVER `<div onClick>` or `<span onClick>`.
- Navigation uses `<a href>`. NEVER a `<div>` with a click handler.
- Use landmarks: `<header>`, `<nav>`, `<main>`, `<aside>`, `<footer>`.
- Use real headings `<h1>`–`<h6>` in order; never skip a level. One `<h1>` per page.
- Lists use `<ul>`/`<ol>`/`<li>`. Tabular data uses `<table>`/`<th scope>`/`<td>`.
- Forms use `<input>`/`<select>`/`<textarea>` with an associated `<label>`.
- Reach for ARIA only when no native element fits. Prefer semantics over ARIA.

### Accessible names — every interactive element must have one
- Icon-only buttons: add `aria-label` (e.g. `aria-label="Close dialog"`), and
  put `aria-hidden="true"` on the decorative SVG/icon inside.
- Images: meaningful `alt` for functional images; `alt=""` for decorative ones.
- Inputs: a visible `<label>`, or `aria-label`/`aria-labelledby` if none is shown.
- Links: descriptive text — never "click here" or "read more" alone.

### State and relationships — expose state to assistive tech, not just CSS
- Disclosures/accordions: `aria-expanded` on the trigger, `aria-controls`
  pointing to the panel. A chevron rotation is NOT a state.
- Toggles: `aria-pressed` (button) or `role="switch"` + `aria-checked`.
- Selected items: `aria-selected` / `aria-current` as appropriate.
- Dialogs: `role="dialog"` (or native `<dialog>`), `aria-modal="true"`, an
  `aria-labelledby` title, a focus trap, and Escape-to-close.

### Keyboard — everything works without a mouse
- Every interactive element is focusable and operable by keyboard.
- If you must attach a click handler to a non-button element, also handle
  `onKeyDown` for Enter and Space and give it `tabindex="0"` and a `role`.
  (Prefer just using a `<button>`.)
- Composite widgets (menus, tabs, listboxes, radio groups) support arrow keys.
- Modals/overlays trap focus, close on Escape, and return focus to the trigger.
- Never remove focus outlines without providing a visible replacement.

### Color, contrast, and motion
- Text contrast ≥ 4.5:1 (≥ 3:1 for large text). UI/graphics contrast ≥ 3:1.
  This includes placeholder text — do not ship faint gray placeholders.
- Never convey information by color alone; add text, icon, or pattern.
- Wrap non-essential animation in `prefers-reduced-motion` (or use Tailwind's
  `motion-safe:` / `motion-reduce:` variants).
- Interactive targets are ≥ 24×24px (or spaced to avoid overlap).

### Prefer accessible primitives over hand-rolled ARIA
For any complex widget (dialog, menu, combobox, listbox, tabs, tooltip,
disclosure, date picker), use a battle-tested headless library instead of
building ARIA from scratch: Radix UI, Headless UI, or React Aria. These encode
correct roles, states, and keyboard behavior into the component contract.

### Write testable markup
- Tests query by role and accessible name (`getByRole('button', { name })`),
  never by `data-testid`. If a `getByRole` query is hard to write, the markup
  is probably not accessible — fix the markup, not the test.
```

---

## After you add the rules

Rules files raise the floor but don't guarantee compliance — models still drift. Back them with the automated layers so violations get caught mechanically:

1. **Lint** — `eslint-plugin-jsx-a11y` at error level (see `references/testing-tools-and-techniques.md`).
2. **Runtime tests** — `jest-axe` / `@axe-core/playwright` on rendered components.
3. **CI gate** — fail the build on lint or axe violations.
4. **Manual pass** — automation covers ~70–85% of issues; the rest needs keyboard + real screen reader testing (see SKILL.md, Layers 2–3).

## When the agent ignores the rules

- **Targeted follow-up:** "This button is a `<div>` — make it a real `<button>` with keyboard support."
- **Audit prompt:** "Review this component for WCAG 2.2 AA violations and list each one with the criterion it breaks."
- **Escalate to a primitive:** "Rebuild this custom select using Headless UI's `Listbox`."
