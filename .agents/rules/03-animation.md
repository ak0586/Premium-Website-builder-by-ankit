---
trigger: always_on
---

---
trigger: always_on
---

## Core Requirement: Fully Animated Website

Every client website must be designed and implemented as a motion-rich experience.

A website should not feel static.

Motion should be present throughout the complete user journey, including:

- initial page load
- page transitions
- navigation
- hero
- headings
- text
- images
- sections
- cards
- buttons
- links
- forms
- menus
- interactive components
- hover states
- focus states
- scroll interactions
- section transitions
- content reveals
- image transitions
- loading states
- success/error states
- footer
- other meaningful interface interactions

The goal is not to animate every element continuously.

The goal is:

> The entire website should feel alive, fluid, responsive, and intentionally animated.

Motion should create continuity between elements and sections rather than appearing as isolated animation effects.

---

## Smooth Motion Is Mandatory

Animations should feel smooth, natural, and professionally choreographed.

Avoid:

- abrupt movement
- mechanical transitions
- excessive bouncing
- random delays
- inconsistent easing
- overly fast entrances
- unnecessary long animations
- animation that feels like a demonstration of a library
- disconnected animations where every element moves independently

Prefer:

- natural easing
- coordinated timing
- consistent motion language
- appropriate duration
- subtle acceleration/deceleration
- smooth transitions between interface states
- meaningful sequencing
- visual continuity
- responsive interaction feedback

Motion should feel intentional rather than mechanically triggered.

---

## Motion Throughout the Experience

Every major part of the website should have an appropriate motion behavior.

### Page Load

The initial experience should establish the website's motion personality.

Consider:

- page entrance
- hero reveal
- typography reveal
- image entrance
- navigation appearance
- coordinated sequencing

Do not create an unnecessarily long loading animation.

---

### Navigation

Navigation should respond smoothly to user interaction.

Consider:

- hover transitions
- active states
- mobile menu opening/closing
- menu item reveals
- sticky navigation transitions
- scroll-state changes

---

### Hero

The hero should generally be one of the strongest motion areas.

Potential techniques include:

- staged text reveals
- image/media entrance
- subtle image movement
- CTA transitions
- layered movement
- controlled background motion
- scroll-linked behavior

Do not overload the hero with unrelated effects.

---

### Content Sections

Sections should not simply appear as static blocks.

Use appropriate:

- reveal transitions
- staggered content
- image reveals
- text transitions
- directional movement
- scroll-linked effects
- section-to-section continuity

The animation should support the hierarchy of the content.

---

### Components

Interactive components should provide smooth feedback.

Examples:

- buttons
- cards
- tabs
- accordions
- forms
- dropdowns
- navigation
- image galleries
- filters
- sliders
- dialogs

Every meaningful interactive state should have an appropriate transition where technically and contextually appropriate.

---

### Scroll Experience

Scrolling should feel connected and intentional.

Possible techniques include:

- section reveals
- progressive content movement
- subtle parallax
- image movement
- sticky storytelling
- scroll-linked transformations
- smooth section transitions

Do not automatically add heavy parallax or smooth-scroll libraries.

Choose techniques based on the project's creative direction and performance requirements.

---

### Footer

The footer should not be treated as an unanimated afterthought.

Use subtle transitions for:

- links
- interactive elements
- content appearance
- agency attribution
- navigation

The final section should feel like part of the same motion system.

---

## Motion Continuity

Animations across the website should feel like they belong to the same system.

Define:

- motion personality
- easing philosophy
- duration ranges
- reveal direction
- stagger behavior
- hover behavior
- scroll behavior
- page transition behavior

Avoid creating every animation independently.

The website should feel choreographed rather than assembled from unrelated effects.

---

## Client-Specific Motion Personality

Every project must have a motion personality appropriate to the client.

Possible characteristics include:

- calm
- elegant
- premium
- energetic
- playful
- editorial
- cinematic
- technical
- precise
- luxurious
- warm
- authoritative
- experimental

The motion personality should be determined by:

- industry
- audience
- brand
- positioning
- content
- visual identity
- conversion goals
- cultural context

Do not use the same animation style for every client.

---

## Category-Specific Motion Concepts (Required)

A motion personality (calm, energetic, luxurious, etc.) is necessary
but not sufficient. Beyond tone, every project must derive a
**category-specific motion concept**: a small set of motion ideas
rooted in the physical or conceptual characteristics of the client's
actual industry, so that the animation communicates what the business
*is*, not just how it feels.

> Animation should communicate the identity of the business.
> Not: animation should simply make the page move.

Before implementing animation on a client project:

1. Derive the motion concept using the six-question method in
   [`design-system/category-motion.md`](../../design-system/category-motion.md#3-motion-concept-derivation-required-before-implementation).
2. Consult the industry motion bank in that same file for inspiration
   — treat every entry there as a starting point, never as a template
   to copy directly.
3. Record the resulting motion concept in the client design brief
   (Section 10, Motion Concept Derivation) before major implementation
   begins.

Two clients in the same industry must not receive the same execution.
The category supplies semantic material; the client's brand,
positioning, audience, and content determine the final result.

Category-derived motion must remain sophisticated and metaphorical,
never literal or gimmicky (cartoon objects, things flying across the
screen, decorative spinning with no relationship to the business). See
`design-system/category-motion.md` Section 7 for concrete good/bad
examples.

If a proposed animation would work identically on a direct competitor
in the same industry, it has not been made specific enough — return to
the six-question derivation and continue.

---

## Animation Hierarchy

Use multiple levels of motion:

1. **Micro motion**
   - buttons
   - links
   - icons
   - controls
   - feedback

2. **Component motion**
   - cards
   - menus
   - forms
   - galleries
   - dialogs

3. **Section motion**
   - content reveals
   - image movement
   - section transitions
   - scroll-linked effects

4. **Page motion**
   - page entrance
   - route transitions
   - major navigation transitions

5. **Brand motion**
   - distinctive movement language
   - signature transitions
   - unique interactions
   - category-specific motion concept (see above)

6. **Ambient motion**
   - subtle background movement
   - media movement
   - atmospheric effects

Ambient and decorative motion should remain controlled.

---

## Motion Must Not Become Visual Noise

"Fully animated" does not mean:

- everything constantly moves
- every section uses a different effect
- every scroll event triggers an animation
- every element has parallax
- every card floats
- every heading spins or scales
- excessive stagger delays
- continuous looping animations everywhere

The user should notice the **quality and fluidity of the experience**, not the number of animations.

---

## Performance

Prefer performant animation techniques.

Prioritize properties such as:

- transform
- opacity

Use GPU-friendly techniques where appropriate.

Avoid unnecessarily animating:

- layout-heavy properties
- expensive filters
- large-area blur effects
- excessive box-shadow transitions
- expensive DOM operations
- unnecessary JavaScript animation loops

Animation must not significantly degrade:

- loading performance
- scrolling
- interaction responsiveness
- mobile performance
- battery usage

---

## Reduced Motion

Respect:

`prefers-reduced-motion`

When reduced motion is enabled:

- reduce movement
- remove non-essential motion
- shorten transitions
- preserve usability
- preserve important state changes

The website should remain fully usable without decorative motion.

---

## Animation Technology

Choose the smallest appropriate technology.

Possible tools include:

- CSS transitions
- CSS animations
- Motion
- GSAP
- Lenis
- React Bits
- Magic UI
- native browser APIs

Do not use a library merely because it is available.

The technology should support the creative direction rather than determine it.

---

## Final Motion Test

Before considering a website complete, ask:

- Does the website feel alive?
- Is motion present throughout the experience?
- Does the page load feel intentional?
- Does navigation respond smoothly?
- Do major sections transition naturally?
- Do interactive elements provide feedback?
- Does scrolling feel connected?
- Does the footer feel integrated into the motion system?
- Do animations feel like one coherent language?
- Is the motion appropriate for this particular client?
- Does the website have a category-specific motion concept, or only a
  generic motion personality?
- Would this motion concept work unchanged on a direct competitor? If
  so, it is not specific enough.
- Does anything feel excessively animated?
- Does anything feel mechanically animated?
- Does anything look like a generic AI animation template?
- Does the website remain smooth on mobile?
- Does reduced-motion behavior work correctly?

The final experience should feel:

> **smooth, fluid, cohesive, responsive, intentional, and professionally art-directed.**
