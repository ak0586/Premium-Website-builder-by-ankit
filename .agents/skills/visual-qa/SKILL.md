---
name: visual-qa
description: Inspects rendered websites across mobile, tablet, laptop, and desktop viewports to identify visual, typography, spacing, color, imagery, responsive, interaction, motion, and generic AI-aesthetic issues.
---

# Visual QA Skill


## Purpose

Use this skill when the rendered website needs visual inspection and refinement.

Visual QA must be based on the actual rendered result.

Do not assume that correct code automatically produces a good interface.

## Inspection

Inspect the website at minimum at:

- mobile
- tablet when relevant
- desktop
- large desktop when relevant

Check the actual rendered result rather than relying only on source code.

## Check

### Composition

Look for:

- awkward spacing
- weak hierarchy
- empty areas
- overcrowding
- misalignment
- inconsistent containers
- repetitive section patterns

### Typography

Check:

- font rendering
- heading scale
- line length
- line height
- hierarchy
- wrapping
- mobile readability

### Color

Check:

- contrast
- visual balance
- accent usage
- consistency
- readability

### Components

Check:

- buttons
- cards
- forms
- navigation
- inputs
- icons
- states
- AI concierge widget:
  - presence and visibility across all viewports
  - bespoke, on-brand styling and avatar (not a generic third-party chat bubble)
  - modal and conversation panel render cleanly without clipping
  - zero visual clash or physical overlap with primary CTAs, sticky mobile contact bars, or nav controls
  - readable typography and clear interactive states (chat input, voice push-to-talk, close button)

### Imagery

Check:

- crop
- aspect ratio
- quality
- loading
- alignment
- relationship to surrounding content

### Motion

Check:

- entrance timing
- hover behavior
- scroll effects
- transitions
- excessive movement
- layout shifts
- 2D-first craft default (any 3D moment is justified and performs smoothly)

Motion should feel intentional and natural.

## Responsive QA

Check for:

- horizontal overflow
- broken grids
- clipped text
- oversized headings
- cramped buttons
- navigation problems
- incorrect image crops
- excessive spacing
- touch-target problems
- AI concierge widget positioning (adequate clearance from mobile sticky CTA bars)

## Priority

Fix issues in this order:

1. broken functionality
2. layout problems
3. responsive problems
4. typography
5. hierarchy
6. spacing
7. imagery
8. interaction
9. motion
10. decorative polish

Do not polish decorative details while major layout issues remain.

## AI Aesthetic Check

Ask:

- Does the site look like a generic AI-generated template?
- Are there too many gradients?
- Are there too many rounded cards?
- Are there unnecessary floating elements?
- Is animation excessive?
- Is every section visually identical?
- Is there enough visual restraint?

If yes, simplify and redesign rather than adding more effects.

## Verification Rule

Only state that visual QA was completed after actually inspecting the rendered result.