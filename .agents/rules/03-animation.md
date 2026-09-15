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

## Required Technique Floor

Every website built in this system must implement ALL of the following
techniques as a minimum standard. These are not optional enhancements.

### Hero

- **Wipe-reveal or clip-path entrance** on the primary headline (e.g.
  `clipPath: 'inset(0 100% 0 0)'` → `inset(0 0% 0 0)` sweep). The direction
  and angle should be derived from the category-specific motion concept.
- **Scroll-linked parallax** on the hero background image using
  `useScroll` + `useTransform` (5–18% relative travel).
- **Scroll-linked opacity fade-out** on hero content as the user
  scrolls past — `useTransform(scrollYProgress, [0, 0.6], [1, 0])`.
- **Staggered entrance sequence** for eyebrow → headline → subheadline → CTA
  → trust line (delays: 0.2, 0.4–0.6, 0.9, 1.05, 1.2s).

### Navigation

- **Scroll-aware glass transition**: transparent at top → dark/blurred backdrop
  after 60px scroll. CSS `transition` on `background-color` and
  `backdrop-filter`.
- **Animated link underlines**: CSS `::after` pseudo-element with
  `scaleX` or `right` transition from 100% to 0%.
- **Mobile drawer**: `AnimatePresence` + `motion.div` slide or fade.

### Content Sections

- **Scroll-triggered fade-up**: Every section's text content fades up
  via `useInView` with `once: true`. Default: `opacity 0→1`, `y 24→0`,
  `duration 0.7–0.8s`, `ease [0.16, 1, 0.3, 1]`.
- **Staggered children**: Where sections contain a grid/list, each child
  staggers by `(index % cols) * 0.1s`.
- **Image sweep-in**: Editorial split-layout images use a clip-path
  sweep from the outer edge. Direction alternates L/R across sections.
- **Accent marks**: Decorative borders, lines, or circles use `scaleY`
  or `scaleX` entrance triggered by scroll (`transform-origin: top`).

### Cards & Interactive Elements

- **Hover lift**: Cards translate `translateY(-3–6px)` on hover with
  `transition: transform 0.3s ease`.
- **Accent reveal**: A colored border/line (e.g. top or left edge)
  expands from 0 to 100% on hover via `height` or `width` CSS transition.
- **Icon state transition**: Icons within cards respond to parent hover
  (color change, background shift) via CSS transitions.

### Trust Bar / Stats

- **Stagger scroll reveal**: Each stat fades up with index-based delay
  using `useInView`. For count-up number animation, use React Bits or
  GSAP `gsap.to({ val: 0 }, { val: target })` on scroll entry.

### AI Concierge Avatar

- **4 CSS-animated SVG states**: idle (ambient breath), listening
  (pulse arcs), thinking (rotating arc), speaking (waveform bars).
  All CSS `@keyframes`, zero JS runtime cost.
- **Launcher pulse**: The widget launcher button has a subtle ambient
  glow or scale animation when in idle state.

### Ambient / Brand Mark

- **One atmospheric brand element**: A single category-derived ambient
  mark (diagonal line, arc, geometric shape) that appears in the hero
  via `scaleX` or `opacity` entrance and then persists. Must be derived
  from the motion concept, not added generically.

### Footer

- **Link hover transitions**: All footer links have CSS `color`
  transitions on hover.
- **Reveal on scroll entry**: Footer content fades in via `useInView`.

---

## Reference Implementation

> **`e:\clients-websites\devaki-dental-v2\`** is the canonical reference
> implementation for this technique floor. Every technique in the
> "Required Technique Floor" section above is demonstrated there.
> Read the source code of any component you are implementing to
> understand how the technique was applied in context.

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

## Animation Technology — Primary Required Stack

> [!IMPORTANT]
> The following four technologies are the **primary required animation stack**
> for every client website built in this system. They are not optional additions
> — they are the standard implementation foundation.

### 1. Motion (Framer Motion) — Scroll-Triggered Reveals & Choreography

Use for:

- `useInView` + `motion.div` scroll-triggered reveals on every content section
- `useScroll` + `useTransform` for scroll-linked parallax (hero images, content fade-out)
- `AnimatePresence` for component mount/unmount (nav mobile drawer, concierge widget, modals)
- Stagger choreography via `variants` with `staggerChildren`
- Page-load entrance sequences (hero, nav)
- Clip-path wipe-reveal animations for headlines and section imagery

Install: `npm install framer-motion`

### 2. GSAP — Timeline Choreography & Advanced Scroll

Use for:

- Complex timeline sequences that need precise per-element control
- `ScrollTrigger` for scroll-driven storytelling (pin-and-scrub, progress-linked transforms)
- Multi-step entrance choreographies where framer-motion stagger is insufficient
- Smooth counters, path morphs, and SVG stroke animations
- Hero text character/word split animations (`SplitText` or manual span splitting)

Install: `npm install gsap`

> [!NOTE]
> Use Motion for declarative React-native scroll reveals. Use GSAP when you need
> imperative, timeline-based control or advanced ScrollTrigger capabilities.
> They coexist cleanly in the same project.

### 3. React Bits — Elevated Micro-Interactions & Text Effects

Use for:

- Text reveal and split effects that feel premium (letter-by-letter, word-by-word)
- Hover interaction patterns (magnetic buttons, cursor follow effects)
- Count-up number animations (stat counters, trust bars)
- Animated backgrounds (mesh gradients, particle fields — when justified by creative direction)
- Transition overlay patterns between route changes

Reference: https://www.reactbits.dev

### 4. CSS Animations & SVG Keyframes — Avatar States & Ambient Motion

Use for:

- All animated bot/concierge avatar states (idle breath, listening pulse, thinking spin, speaking waveform) — CSS keyframes only, no JS runtime cost
- Ambient decorative brand marks (diagonal light lines, rotating circles, atmospheric elements)
- Nav link underline hover transitions
- Button micro-interactions (scale, border-color, background transitions)
- Loading spinners and progress indicators
- Any continuous looping animation (CSS, not JS)

**Rule**: Any continuously looping animation MUST use CSS `@keyframes`, never a JavaScript `requestAnimationFrame` loop.

### Supporting & 3D Tools

- **Three.js**: **Mandatory for every website** — implement a bespoke, smooth, hardware-accelerated 3D scene directly tailored to the client's medical/business specialization (e.g. dermal cellular matrix for dermatology, enamel prism for dental, joint kinematics for orthopedics, aerodynamic flow for auto). **Every website must have a UNIQUE 3D effect.** Clean up resources on unmount (`geometry.dispose()`, `material.dispose()`, `renderer.dispose()`).
- **Lenis**: Required for smooth momentum scroll on all projects. Install: `npm install lenis`. Load asynchronously after LCP.
- **Lottie / Rive**: For complex vector animations (AI avatar if SVG keyframes are insufficient, icon animations, brand spot animations).

### Technology Selection Rule

Every project must implement this full stack:
```
Three.js + GSAP + Motion (Framer Motion) + React Bits + CSS/SVG + Lenis
```

Do not skip Three.js or reduce the stack to a simple 2D template. Every client website requires a bespoke Three.js 3D moment and signature interactive components (3D cylinder carousel with bespoke SVGs, smooth before/after sliders, magnetic cursor).

---

## Final Motion Test

Before considering a website complete, ask:

- Does the website feel alive and premium?
- Is a bespoke Three.js 3D animation implemented, and is it unique to this client's specialization?
- Is Three.js properly disposed on unmount with zero memory leaks?
- Are navigation buttons strictly on a single line (`white-space: nowrap`) with zero wrapping?
- Is the Ushera AI concierge widget present with its compact avatar + name launcher?
- Has redundant static consultation form clutter been removed in favor of Ushera?
- Is motion present throughout the complete journey without lagging?
- Does the website remain smooth (60fps) on mobile, specifically verified on
  a simulated throttled/low-end device profile (e.g. ₹8k–15k Android phone)?
- Does reduced-motion behavior work correctly?

The final experience should feel:

> **smooth, fluid, cohesive, responsive, intentional, and professionally art-directed.**
