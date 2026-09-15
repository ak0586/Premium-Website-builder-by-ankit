# Motion Design System

## 1. Purpose

Motion should communicate, guide and refine the experience.

It should not exist merely to demonstrate technical capability.

---

## 2. Motion Personality

Motion can contribute to brand personality.

Examples:

### Calm / Clinical

Prefer:

- soft fades
- subtle transforms
- restrained timing
- gentle image reveals

### Luxury / Editorial

Prefer:

- elegant reveals
- controlled movement
- sophisticated transitions
- deliberate pacing

### Technical / Automotive

May support:

- sharper transitions
- directional movement
- stronger interaction feedback

### Playful

May support:

- expressive transitions
- playful micro-interactions
- more noticeable movement

These are examples, not fixed templates.

---

## 2a. Category-Specific Starting Points

Motion personality (Section 2) describes *tone*. It does not by
itself make motion specific to the client's business.

Before implementation, derive a category-specific motion concept using
the six-question method and industry motion banks in
[`design-system/category-motion.md`](./category-motion.md). That file
is the canonical reference — do not duplicate its content here.

Two rules carry over from that file into every project:

- The industry motion banks are inspiration, never templates. Two
  clients in the same industry must not receive the same execution.
- Reject any candidate motion idea that is decoration with no
  relationship to the business, even if it looks technically
  impressive.

---

## 2b. 2D-First Motion & Lightweight Depth (Default)

The default motion architecture for all client websites is **2D-first,
motion-rich, and built on lightweight depth**.

For small local businesses (clinics, barbers, auto/bike workshops,
salons, cafes, neighborhood services), the majority of visitors browse
on budget or mid-tier mobile devices (e.g. ₹8k–15k Android phones on
variable mobile networks). The motion design must deliver immediate,
silky fluidity without heavy canvas calculations or battery drain.

### Core Techniques

- **Scroll-Triggered Reveals**: Content sections and cards enter smoothly
  via coordinated opacity and subtle translation (e.g. `translate-y: 16–28px`
  over 0.6–0.8s with `power2.out` or natural cubic-bezier easing).
  Stagger child items predictably (`0.08–0.12s` intervals).
- **Image Movement & Parallax**:
  - Subtle scroll parallax on photography (e.g. 5–15% relative travel
    between image and container).
  - Gentle scale-on-hover on service cards and gallery items (e.g.
    `scale: 1.02–1.03` with smooth ease-out).
  - Slow, restrained Ken-Burns zoom on prominent hero imagery.
- **Restrained Text Animation**:
  - Word or line reveals using CSS clip-path or overflow masks.
  - Subtle tracking or weight transitions on key headlines.
  - Never animate every paragraph or character continuously; text motion
    must serve hierarchy, not compete with reading.
- **Micro-Interactions & Tactile Feedback**:
  - Buttons, cards, links, and icons provide instant visual feedback on
    hover, focus, and press (`scale: 0.98`, subtle border glow, or
    lightweight background shift).
- **Lightweight Depth Tricks (Faking the Z-Axis)**:
  - Multi-layer composition: foreground text, mid-ground photography,
    and background atmospheric elements moving at subtly offset scroll
    speeds.
  - Soft blurred ambient shapes and luminous gradients behind cards
    instead of expensive volumetric lighting.
  - Intentional drop shadows, border highlights, and scale contrasts to
    establish spatial depth without a WebGL canvas.
- **Technology Priority**:
  - Prioritize CSS transforms, CSS opacity, native browser animations,
    and lightweight SVG animations.
  - Use small, purpose-built vector animation tools (such as Lottie or
    Rive) for avatars, indicators, and micro-animations.
  - Reserve canvas and WebGL strictly for the rare, justified exception
    described in Section 12.

---

## 2c. Primary Technique Library (Required Reading Before Implementation)

This section documents the concrete, copy-reference animation patterns
that every client website must implement. These are the minimum craft
standards — the floor, not the ceiling.

The **canonical reference implementation** for all patterns below is
`e:\clients-websites\devaki-dental-v2\`. Read the source of any
component you are building to see the exact pattern in full context.

---

### Pattern 1 — Clip-Path Wipe Reveal (Hero Headline)

The signature headline entrance. Text is hidden by a clip rectangle that
sweeps open, like a clinical light (or a spotlight, or a curtain — derive
the metaphor from the category motion concept).

```jsx
// Motion (Framer Motion)
const WipeReveal = ({ children, delay = 0 }) => (
  <div style={{ overflow: 'hidden' }}>
    <motion.div
      initial={{ clipPath: 'inset(0 100% 0 0)' }}
      animate={{ clipPath: 'inset(0 0% 0 0)' }}
      transition={{ duration: 1.1, delay, ease: [0.16, 1, 0.3, 1] }}
    >
      {children}
    </motion.div>
  </div>
)

// Usage — stagger each headline line
<h1>
  <WipeReveal delay={0.4}><span>Line one</span></WipeReveal>
  <WipeReveal delay={0.58}><span>Line two</span></WipeReveal>
</h1>
```

**Variations by motion concept:**
- Horizontal L→R: `inset(0 100% 0 0)` → `inset(0 0% 0 0)` (clinical sweep)
- Horizontal R→L: `inset(0 0 0 100%)` → `inset(0 0 0 0%)` (reveal from right)
- Vertical T→B: `inset(0 0 100% 0)` → `inset(0 0 0% 0)` (curtain drop)
- Diagonal: combine with `rotate` on a parent wrapper

---

### Pattern 2 — Scroll-Linked Hero Parallax + Fade-Out

The hero image moves at a slower rate than scroll, and the content
fades as the user leaves the hero.

```jsx
// Motion (Framer Motion)
const ref = useRef(null)
const { scrollYProgress } = useScroll({
  target: ref,
  offset: ['start start', 'end start']
})

const imageY    = useTransform(scrollYProgress, [0, 1], ['0%', '18%'])
const contentY  = useTransform(scrollYProgress, [0, 1], ['0%', '8%'])
const opacity   = useTransform(scrollYProgress, [0, 0.6], [1, 0])

// Apply:
<section ref={ref}>
  <motion.div style={{ y: imageY }}> {/* background image wrapper */} </motion.div>
  <motion.div style={{ y: contentY, opacity }}> {/* hero content */} </motion.div>
</section>
```

---

### Pattern 3 — Scroll-Triggered Fade-Up (Section Content)

Every text block in every section uses this as the baseline entrance.

```jsx
// Motion (Framer Motion)
const FadeUp = ({ children, delay = 0 }) => {
  const ref = useRef(null)
  const inView = useInView(ref, { once: true, margin: '-60px' })

  return (
    <motion.div
      ref={ref}
      initial={{ opacity: 0, y: 24 }}
      animate={inView ? { opacity: 1, y: 0 } : {}}
      transition={{ duration: 0.8, delay, ease: [0.16, 1, 0.3, 1] }}
    >
      {children}
    </motion.div>
  )
}
```

**Standard delay cascade for a section header:**
- Label: `delay={0}`
- H2 heading: `delay={0.12}`
- Body paragraph 1: `delay={0.24}`
- Body paragraph 2: `delay={0.36}`
- CTA button: `delay={0.46}`

---

### Pattern 4 — Staggered Grid Children

For service cards, pillar grids, testimonial grids, and any repeating
layout where children should enter sequentially.

```jsx
// Column-aware stagger — items in the same column share delay,
// preventing visual "waterfall" in a 3-col grid
{items.map((item, i) => (
  <motion.div
    key={item.id}
    ref={ref}
    initial={{ opacity: 0, y: 28 }}
    animate={inView ? { opacity: 1, y: 0 } : {}}
    transition={{
      duration: 0.7,
      delay: (i % cols) * 0.1,  // cols = 1 | 2 | 3
      ease: [0.16, 1, 0.3, 1]
    }}
  />
))}
```

---

### Pattern 5 — Image Sweep-In (Editorial Split Layout)

For About sections and split-layout image+text compositions.

```jsx
// Motion (Framer Motion)
const SweepIn = ({ children, delay = 0, direction = 'left' }) => {
  const ref = useRef(null)
  const inView = useInView(ref, { once: true, margin: '-80px' })

  return (
    <motion.div
      ref={ref}
      initial={{
        clipPath: direction === 'left' ? 'inset(0 100% 0 0)' : 'inset(0 0 0 100%)',
        opacity: 0
      }}
      animate={inView ? { clipPath: 'inset(0 0% 0 0%)', opacity: 1 } : {}}
      transition={{ duration: 1, delay, ease: [0.16, 1, 0.3, 1] }}
    >
      {children}
    </motion.div>
  )
}
```

---

### Pattern 6 — Scroll-Aware Nav Glass Transition

```css
/* CSS only — no JS needed */
.header {
  position: fixed;
  top: 0;
  transition:
    background-color 0.4s ease,
    backdrop-filter 0.4s ease,
    border-color 0.4s ease;
  border-bottom: 1px solid transparent;
}

.header.scrolled {
  background-color: rgba(15, 17, 23, 0.88);
  backdrop-filter: blur(20px) saturate(160%);
  border-bottom-color: var(--color-border-dark);
}
```

```js
// React hook
const [scrolled, setScrolled] = useState(false)
useEffect(() => {
  const handler = () => setScrolled(window.scrollY > 60)
  window.addEventListener('scroll', handler, { passive: true })
  return () => window.removeEventListener('scroll', handler)
}, [])
```

---

### Pattern 7 — Hover Card Accent Reveal

A colored border line that grows from 0 to 100% on hover. The accent
direction (top, left) should be derived from the design system.

```css
.card { position: relative; overflow: hidden; }

/* Left accent — grows vertically */
.cardAccent {
  position: absolute;
  top: 0; left: 0;
  width: 3px; height: 0;
  background: var(--color-accent);
  transition: height 0.5s cubic-bezier(0.16, 1, 0.3, 1);
}

.card:hover .cardAccent { height: 100%; }

/* Top accent — grows horizontally */
.cardAccentTop {
  position: absolute;
  top: 0; left: 0;
  height: 2px; width: 0;
  background: var(--color-accent);
  transition: width 0.5s cubic-bezier(0.16, 1, 0.3, 1);
}

.card:hover .cardAccentTop { width: 100%; }
```

---

### Pattern 8 — Animated Link Underline

```css
.navLink {
  position: relative;
  padding-bottom: 2px;
}

.navLink::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  right: 100%;
  height: 1px;
  background: var(--color-accent);
  transition: right 0.3s cubic-bezier(0.16, 1, 0.3, 1);
}

.navLink:hover::after { right: 0; }
```

---

### Pattern 9 — CSS SVG Avatar States

All four states of the AI concierge avatar MUST be CSS `@keyframes` only.
No JS runtime cost.

```css
/* Idle — ambient breathing on outer ring */
@keyframes breathe {
  0%, 100% { opacity: 0.2; transform: scale(1); }
  50%       { opacity: 0.4; transform: scale(1.04); }
}
.idle .outerRing { animation: breathe 3s ease-in-out infinite; }

/* Listening — expanding pulse arcs */
@keyframes pulse1 {
  0%   { opacity: 0.6; transform: scale(1); }
  70%  { opacity: 0;   transform: scale(1.35); }
}
.listening .pulseArc1 { animation: pulse1 1.4s ease-out infinite; }
.listening .pulseArc2 { animation: pulse1 1.4s ease-out infinite 0.3s; }

/* Thinking — spinning dashed arc */
@keyframes spin {
  from { transform: rotate(0deg); }
  to   { transform: rotate(360deg); }
}
.thinking .thinkingArc {
  transform-origin: center;
  animation: spin 1.6s linear infinite;
}

/* Speaking — waveform bars */
@keyframes barPulse {
  0%, 100% { transform: scaleY(0.5); }
  50%      { transform: scaleY(1); }
}
.speaking .bar { animation: barPulse 0.6s ease-in-out infinite; }
.speaking .bar:nth-child(2) { animation-delay: 0.1s; }
.speaking .bar:nth-child(3) { animation-delay: 0.2s; }

/* Always disable all animation for reduced motion */
@media (prefers-reduced-motion: reduce) {
  .avatarWrap * { animation: none !important; }
}
```

---

### Pattern 10 — GSAP Counter Animation (Stats)

For trust bars and any numeric stat that should count up on scroll entry.

```jsx
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger)

useEffect(() => {
  const el = counterRef.current
  const obj = { val: 0 }
  gsap.to(obj, {
    val: targetNumber,
    duration: 1.4,
    ease: 'power2.out',
    scrollTrigger: {
      trigger: el,
      start: 'top 80%',
      once: true,
    },
    onUpdate() {
      el.textContent = Math.round(obj.val).toLocaleString()
    }
  })
}, [targetNumber])
```

---

### Pattern 11 — GSAP Word Split Reveal (Headlines)

For premium editorial headline reveals beyond the clip-path sweep.

```jsx
import { gsap } from 'gsap'
import { SplitText } from 'gsap/SplitText' // requires GSAP Club or manual span split
gsap.registerPlugin(SplitText)

useEffect(() => {
  if (!headlineRef.current) return
  const split = new SplitText(headlineRef.current, { type: 'words' })
  gsap.from(split.words, {
    opacity: 0,
    y: 24,
    duration: 0.7,
    stagger: 0.06,
    ease: 'power3.out',
    scrollTrigger: {
      trigger: headlineRef.current,
      start: 'top 80%',
      once: true,
    }
  })
  return () => split.revert()
}, [])
```

**Alternative without GSAP Club** — manual `<span>` split:

```jsx
const words = text.split(' ')
return (
  <h2>
    {words.map((word, i) => (
      <motion.span
        key={i}
        style={{ display: 'inline-block', marginRight: '0.25em' }}
        initial={{ opacity: 0, y: 20 }}
        animate={inView ? { opacity: 1, y: 0 } : {}}
        transition={{ duration: 0.6, delay: i * 0.06, ease: [0.16, 1, 0.3, 1] }}
      >
        {word}
      </motion.span>
    ))}
  </h2>
)
```

---

### Pattern 12 — Ambient Hero Brand Mark

A single atmospheric element in the hero that communicates the motion
concept. Must be derived from the category-specific motion concept, not
added generically.

```jsx
// Example: diagonal light sweep line (Devaki Dental — "Clinical Illumination")
<motion.div
  className={styles.lightLine}  // diagonal CSS transform, thin gradient line
  initial={{ opacity: 0, scaleX: 0 }}
  animate={{ opacity: 0.35, scaleX: 1 }}
  transition={{ duration: 2, delay: 0.3, ease: [0.16, 1, 0.3, 1] }}
  aria-hidden="true"
/>
```

```css
.lightLine {
  position: absolute;
  top: 0; left: -20%; right: -20%;
  height: 1px;
  background: linear-gradient(90deg, transparent 0%, var(--color-accent) 50%, transparent 100%);
  transform: rotate(-25deg) translateY(45vh);
  transform-origin: center;
}
```

**Other category-derived examples:**
- Barber: slow rotating scissor outline
- Automotive: horizontal speed line sweeping left to right once
- Architect: grid lines assembling from grid intersection points
- Yoga: breath-synchronized expanding/contracting circle

---



---

## 3. Motion Hierarchy

### Micro

- hover
- focus
- button feedback
- icon transitions

### Component

- menus
- dialogs
- accordions
- tabs
- AI concierge widget (see [`design-system/chatbot-widget.md`](./chatbot-widget.md))

### Section

- reveals
- image transitions
- staggered content

### Brand

- hero motion
- major visual transitions
- category-specific motion concept (see Section 2a)

### Decorative

- backgrounds
- large effects
- continuous movement

Most websites should emphasize micro, component and restrained
section motion.

---

## 4. Timing

Motion should feel responsive.

Avoid:

- extremely slow transitions
- unnecessary delays
- excessive stagger
- animation that blocks interaction

Use timing appropriate to the interaction.

---

## 5. Easing

Prefer natural-feeling easing.

Avoid excessive use of dramatic or elastic easing when it does not fit
the brand.

---

## 6. Movement

Prefer subtle movement.

Avoid large movement unless the creative direction explicitly calls
for it.

---

## 7. Scroll Motion

Scroll-based motion should reinforce the content.

Do not use scroll effects merely because they look impressive in a
demo.

---

## 8. Continuous Animation

Continuous animation consumes attention.

Use it sparingly.

A continuously moving element should have a clear purpose.

---

## 9. Reduced Motion

Every motion system must support:

`prefers-reduced-motion`

The reduced-motion experience should remain complete and usable.

---

## 10. Performance

Prefer efficient animation.

Avoid unnecessary:

- layout recalculation
- large blur effects
- heavy canvas effects
- continuous JavaScript loops
- excessive animated elements

---

## 11. Motion Consistency

Once a client motion language is established, use it consistently.

Do not combine unrelated animation styles without a reason.

---

## 12. Cinematic 3D Motion & WebGL Storytelling (Opt-In Exception Path)

**IMPORTANT: This is an opt-in exception path, NOT the default baseline.**

Apply 3D WebGL / Canvas storytelling **only** when the project satisfies
the explicit gating criteria in `.agents/rules/01-premium-design.md`
(Section 3a):
1. The client's brand and industry genuinely call for it (e.g. high-end
   cosmetic surgery, luxury dental studio, flagship architecture).
2. The project has allocated budget for the specialized 3D modeling,
   rigging, and cross-browser QA required.
3. **Crucially: It must not compromise performance for the client's
   actual audience on budget/mid-tier mobile devices.** If the target
   audience predominantly browses on modest smartphones (e.g. ₹8k–15k
   Android devices on mobile data), 3D must be rejected in favor of the
   2D-first motion system (Section 2b).

When those gating criteria are fully satisfied:

### Macro-to-Micro Camera Journeys
- Begin with an extreme macro close-up exploring physical surface textures, translucency, and natural microscopic details under soft studio lighting.
- Pull back smoothly along a cinematic camera curve to reveal the full object in space.
- Preserve generous negative space (e.g. 40% visual object, 60% typography and breathing room).

### Physical Materials & Optical Realism
- Avoid the artificial "glossy plastic CGI" look.
- Use physically based materials: realistic subsurface light transmission, refractive index (IOR ~1.62 for enamel), subtle satin roughness, clearcoat moisture sheen, and natural microscopic imperfections.
- Ambient particles should feel like microscopic dust illuminated by soft studio softboxes, never neon sci-fi streaks.

### Interactive Medical & Diagnostic Moments
- Mouse movement should subtly tilt camera perspective and shift specular highlights across physical surfaces.
- Hover states should trigger whisper-thin, elegant diagnostic contours with refined metadata labels (e.g. *"01 / Precision"*, *"02 / Enamel Integrity"*), creating the feel of an advanced optical instrument rather than a video game.

### Subtle Micro-Transformations
- Represent restorative or functional transitions through microscopic changes in surface texture, translucency, and light.
- Never display exaggerated decay, blood, or disturbing medical visuals.

### Scroll-Bound Camera Continuity
- Connect window scroll to camera dolly and translation.
- As the user scrolls, the hero object gracefully transitions into the adjacent section, morphing or revealing architectural interiors with natural daylight and acoustic calm.

This is itself a category-specific motion concept (luxury healthcare)
— treat Section 12 as a worked example of Section 2a, not as a default
to reach for outside that category.

---

## 13. Final Motion Test

Ask:

- Does motion communicate something?
- Does it fit the brand?
- Does it fit the client's specific industry, not just a generic tone?
- **Does this need to be 3D, or would a 2D/parallax/blur technique
  achieve the same premium feeling at a fraction of the performance
  cost?**
- **Have I checked this on a simulated low-end/throttled mobile device?**
- Is it distracting?
- Is it performant?
- Is mobile appropriate?
- Does reduced motion work?
- Would removing it improve the interface?

If removing it improves the interface, remove it.
