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
