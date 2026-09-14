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

### Section

- reveals
- image transitions
- staggered content

### Brand

- hero motion
- major visual transitions

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

## 12. Cinematic 3D Motion & WebGL Storytelling

When the creative direction calls for an ultra-premium, cinematic digital experience (such as luxury healthcare, high-end cosmetic practices, or architectural brands):

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

---

## 13. Final Motion Test

Ask:

- Does motion communicate something?
- Does it fit the brand?
- Is it distracting?
- Is it performant?
- Is mobile appropriate?
- Does reduced motion work?
- Would removing it improve the interface?

If removing it improves the interface, remove it.