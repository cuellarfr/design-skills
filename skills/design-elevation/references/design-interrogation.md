# Design Interrogation Checklist

A systematic framework for questioning and elevating every design decision. Apply these questions before delivering any visual output.

## Foundation Questions

### Purpose & Context
- [ ] Does the design serve its primary purpose without distraction?
- [ ] Is the visual language appropriate for the audience and context?
- [ ] Have I considered the viewing environment (screen, print, projection)?
- [ ] Does it work at different sizes/resolutions?

### First Impressions
- [ ] What would a designer from Pentagram think of this?
- [ ] Does it feel crafted or templated?
- [ ] Is there a clear focal point within 2 seconds?
- [ ] Does it feel premium or generic?

## Typography Interrogation

### Hierarchy
- [ ] Can I scan the content structure in 3 seconds?
- [ ] Are there more than 3 levels of hierarchy? (Usually too many)
- [ ] Is the hierarchy achieved through size, weight, AND spacing?
- [ ] Could I remove a level of hierarchy?

### Type Choices
- [ ] Am I using system fonts by default or by choice?
- [ ] Do the typefaces have the right voice?
- [ ] Is the contrast between sizes dramatic enough?
- [ ] Have I considered optical sizing for display text?

### Refinement
- [ ] Is the line height appropriate for the measure?
- [ ] Are there orphans or widows that break reading flow?
- [ ] Is tracking adjusted for display sizes?
- [ ] Do quotes and apostrophes use proper typography?

## Color Interrogation

### System
- [ ] Is there a clear color logic or is it arbitrary?
- [ ] Am I using pure black (#000000)? (Usually wrong)
- [ ] Do neutrals have subtle temperature?
- [ ] Is the palette accessibility compliant?

### Application
- [ ] Does color serve function or just decoration?
- [ ] Is there semantic meaning to color choices?
- [ ] Could I remove a color and improve clarity?
- [ ] Is color used consistently across similar elements?

### Sophistication
- [ ] Are there subtle color relationships (analogous, triadic)?
- [ ] Do backgrounds use near-whites or near-blacks?
- [ ] Are shadows colored (not just black opacity)?
- [ ] Is there intentional color vibration anywhere?

## Layout Interrogation

### Grid
- [ ] Is there an underlying grid or is placement arbitrary?
- [ ] Are elements aligned to each other intentionally?
- [ ] Does the grid create clear zones and relationships?
- [ ] Is the grid invisible but felt?

### Balance
- [ ] Is visual weight distributed intentionally?
- [ ] Does asymmetry feel deliberate or accidental?
- [ ] Are there dead zones that need activation?
- [ ] Is there enough negative space?

### Flow
- [ ] Is the reading path clear and logical?
- [ ] Do elements lead the eye deliberately?
- [ ] Are related items grouped effectively?
- [ ] Does spacing reinforce relationships?

## Detail Interrogation

### Consistency
- [ ] Are similar elements treated identically?
- [ ] Is there a clear system for variations?
- [ ] Do patterns repeat with intention?
- [ ] Are corner radii, shadows, borders systematic?

### Refinement
- [ ] Are there default software elements showing?
- [ ] Have I replaced generic icons with specific ones?
- [ ] Are transitions and animations purposeful?
- [ ] Do interactive states feel considered?

### Polish
- [ ] Would this look good printed and framed?
- [ ] Are there tiny details that show craft?
- [ ] Does zooming in reveal attention to detail?
- [ ] Have I removed everything unnecessary?

## Data Visualization Interrogation

### Data Integrity (Tufte)
- [ ] Does the visual representation honestly match the numerical data?
- [ ] Is the lie factor between 0.95 and 1.05?
- [ ] Do bar charts start at zero?
- [ ] Are compared charts using identical scales?
- [ ] Are there any 3D effects distorting perception?
- [ ] Is a dual-axis chart creating false correlations? (Use small multiples instead)

### Data-Ink Ratio
- [ ] Can I remove this gridline without losing clarity?
- [ ] Can I remove the chart border/box?
- [ ] Can I remove the background fill?
- [ ] Is there redundant encoding (color AND pattern AND label for the same thing)?
- [ ] Can I replace the legend with direct labels on the data?
- [ ] Are there decorative elements competing with the data?

### Chart Selection
- [ ] Is this the right chart type for this data relationship?
- [ ] Would small multiples be clearer than a multi-series chart?
- [ ] Am I using a pie chart with more than 5 slices? (Switch to bar chart)
- [ ] Would a simple table be more effective than this chart?
- [ ] Does the chart need to exist, or can a single number tell the story?

### Storytelling
- [ ] Does the title state the finding, not the chart type?
- [ ] Is there a clear "so what?" for the viewer?
- [ ] Are key data points annotated with context?
- [ ] Is the source attributed?
- [ ] Are numbers formatted consistently (currency, %, abbreviation)?

### Accessibility
- [ ] Can the data be understood without color alone?
- [ ] Do graphical elements have 3:1 contrast against background?
- [ ] Is a text alternative provided (data table, alt text)?
- [ ] Are red/green used as the only distinguishing pair? (Fix for deuteranopia)
- [ ] Are number columns using tabular-nums for alignment?

## Comparison Questions

### Against Excellence
- [ ] How does this compare to Apple's presentations?
- [ ] Would this fit in Stripe's design system?
- [ ] Does it have Linear's attention to detail?
- [ ] Could this be in a Dieter Rams exhibition?

### Against Defaults
- [ ] What would the generic version look like?
- [ ] How far have I pushed from the template?
- [ ] Which decisions are uniquely mine?
- [ ] What makes this feel expensive?

### Against Expectations
- [ ] Does this exceed what was asked for?
- [ ] Are there delightful surprises?
- [ ] Will the user notice the quality immediately?
- [ ] Does it feel like multiple iterations?

## Final Checks

### The Squint Test
- [ ] Does the hierarchy survive squinting?
- [ ] Are the main zones clear when blurred?
- [ ] Is contrast sufficient throughout?

### The Reduction Test
- [ ] What happens if I remove this element?
- [ ] Can I simplify further without losing function?
- [ ] Is every element earning its space?

### The Context Test
- [ ] Does this feel right for the brand/company?
- [ ] Is it appropriate for the use case?
- [ ] Will it age well or feel dated quickly?

### The Pride Test
- [ ] Would I put this in my portfolio?
- [ ] Would I show this to a design hero?
- [ ] Does this represent excellent craft?
- [ ] Am I genuinely proud of this?

## Red Flags to Fix

- Using pure black text on pure white
- More than 3 font sizes in one view
- Centered text in paragraphs
- Default software colors (Excel blue, PowerPoint orange)
- Inconsistent spacing between elements
- Multiple corner radius values without logic
- Drop shadows without purpose
- Decorative elements without function
- Default system fonts without intention
- Equal spacing everywhere (no hierarchy)
- Icons from different families
- Arbitrary color choices
- Missing hover/active states
- Undefined grid or alignment
- Generic stock imagery
- Default chart styles (Excel blue, Chart.js defaults)
- System UI elements showing
- Pie chart with more than 5 slices
- 3D effects on any chart
- Truncated bar chart baseline
- Dual y-axes creating false correlation
- Chart title describing chart type instead of finding
- Legend requiring eye-scanning back and forth (use direct labels)
- Missing source attribution on data
- Rainbow color palette on categorical data