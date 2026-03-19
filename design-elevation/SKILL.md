---
name: design-elevation
description: Comprehensive design elevation system that automatically transforms functional visual outputs into polished, professional designs. Use when creating ANY visual output including presentations (pptx), spreadsheets (xlsx), dashboards, reports, HTML artifacts, PDFs, web pages, or data visualizations. This skill makes Claude think like a design director who interrogates every design choice, references best practices from leading design systems (Stripe, Linear, Apple, Bauhaus, Swiss design), and systematically elevates outputs from generic to exceptional. Triggers on ALL requests for visual content creation, ensuring outputs look hand-crafted rather than template-based through deliberate typography, color theory, spatial systems, and visual hierarchy decisions.
---

# Design Elevation System

This skill transforms functional visual outputs into polished, professional designs by applying systematic design thinking and refinement protocols.

## Core Philosophy

Think like a design director who wouldn't accept generic output. Every visual element should demonstrate intentional decision-making, from macro-level information architecture to micro-level typographic details.

## Activation Protocol

When creating ANY visual output:

1. **Start with function** - Create a working version first
2. **Apply interrogation** - Question every default choice using `references/design-interrogation.md`
3. **Elevate systematically** - Follow the elevation protocol in `references/elevation-protocol.md`
4. **Reference excellence** - Draw from `references/design-exemplars.md` for inspiration
5. **Apply techniques** - Use specific moves from `references/technique-catalog.md`
6. **Final polish** - Ensure output feels hand-crafted, not templated

## Quick Reference Patterns

### For Presentations (PPTX)
- Start with information hierarchy, not decoration
- Apply grid systems from `references/grid-systems.md`
- Use typography scales from `references/typography-scales.md`
- Reference slide layouts in `assets/presentation-patterns/`

### For Dashboards & Data Visualization
- Begin with data relationships, not chart types
- Apply color systems from `references/color-systems.md`
- Use spacing multipliers from `references/spacing-systems.md`
- Reference dashboard patterns in `assets/dashboard-patterns/`

### For Documents & Reports
- Structure with clear typographic hierarchy
- Apply document grids from `references/document-grids.md`
- Use professional type pairings from `references/type-pairings.md`
- Reference report layouts in `assets/report-patterns/`

### For Web/HTML Artifacts
- Design with responsive grid foundations
- Apply modern CSS techniques from `references/css-techniques.md`
- Use animation restraint principles from `references/animation-principles.md`
- Reference web patterns in `assets/web-patterns/`

## Critical Design Moves

### Typography Excellence
- Never use system defaults without intention
- Apply modular scales (1.25x, 1.333x, 1.5x, 1.618x)
- Create clear hierarchy with weight, size, and spacing
- Use optical adjustments for display text

### Color Sophistication
- Build from neutral foundations (not pure black/white)
- Use color with purpose (semantic, emphasis, wayfinding)
- Apply 60-30-10 rule for color distribution
- Consider accessibility from the start

### Spatial Systems
- Use consistent spacing multipliers (8px, 12px, 16px base units)
- Apply Gestalt principles deliberately
- Create breathing room - density ≠ sophistication
- Use negative space as a design element

### Visual Refinement
- Replace generic icons with purposeful choices
- Use subtle shadows and depth (0-4px typical)
- Apply micro-animations sparingly
- Polish transitions and state changes

## Execution Framework

1. **Initial Assessment**
   - Identify the content type and primary purpose
   - Determine the appropriate design language
   - Select relevant reference materials

2. **Systematic Elevation**
   - Apply grid foundations first
   - Establish typographic hierarchy
   - Build color system
   - Refine spatial relationships
   - Add purposeful embellishments

3. **Quality Checks**
   - Run through interrogation checklist
   - Compare against exemplars
   - Verify accessibility
   - Ensure consistency

## Resource Loading Priority

For efficiency, load resources in this order:
1. `references/elevation-protocol.md` - Always load first
2. `references/technique-catalog.md` - Load for specific techniques
3. `references/design-interrogation.md` - Load for quality checks
4. Context-specific references as needed

## Output Standards

Every delivered visual should:
- Feel intentionally designed, not defaulted
- Show evidence of multiple refinement passes
- Balance boldness with restraint
- Demonstrate systematic thinking
- Look "expensive" through attention to detail

## Silent Execution

Unless explicitly asked, apply all design thinking internally. The user sees only the polished result. Document design decisions in code comments for HTML/CSS, or in speaker notes for presentations, but don't explain the process unless requested.

Remember: Great design is invisible when done right. The user should feel the quality without seeing the effort.