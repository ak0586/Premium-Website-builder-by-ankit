---
trigger: always_on
---

# Animation and Motion Rules

## Purpose

Create motion that feels intentional, refined and appropriate to the
client.

Animation should improve the experience rather than demonstrate that
an animation library was used.

---

## 1. Purpose of Motion

Motion may communicate:

- hierarchy
- continuity
- feedback
- orientation
- state changes
- progressive disclosure
- spatial relationships
- subtle delight

Every significant animation should have a reason.

---

## 2. Default Motion Philosophy

Prefer:

- subtle
- smooth
- restrained
- responsive
- purposeful

Do not animate everything.

A premium website should contain enough motion to feel alive without
becoming distracting.

---

## 3. Motion Hierarchy

Use motion at different levels.

### Level 1 — Micro-interactions

Examples:

- button hover
- icon transitions
- focus changes
- small state changes

### Level 2 — Component transitions

Examples:

- dropdowns
- dialogs
- accordions
- navigation transitions

### Level 3 — Section transitions

Examples:

- section entrance
- image reveal
- staggered content
- subtle scroll interaction

### Level 4 — Hero/brand motion

Use only when appropriate.

### Level 5 — Large decorative effects

Use rarely and only when the creative direction strongly supports
them.

Most projects should primarily use Levels 1–3.

---

## 4. Avoid Animation Overload

Avoid:

- animation on every section
- constant floating elements
- excessive parallax
- random text effects
- continuous background movement
- unnecessary scroll hijacking
- excessive blur animation
- excessive glow effects
- multiple competing animations
- animation that delays content usability

If everything moves, nothing feels important.

---

## 5. Entrance Animations

Entrance animation should generally:

- be brief
- reinforce hierarchy
- avoid delaying interaction
- avoid excessive staggering

Do not make users wait for basic content to become usable.

---

## 6. Hover and Interaction

Hover states should communicate:

- interactivity
- feedback
- hierarchy

They should not become miniature visual effects.

Use subtle:

- color change
- opacity
- transform
- border change
- shadow change

when appropriate.

---

## 7. Scroll Animation

Use scroll-triggered animation selectively.

Good uses:

- revealing content
- creating continuity
- emphasizing important sections
- subtle image movement

Bad uses:

- making every section fly in
- large parallax movement
- hiding content until scrolling
- excessive motion that makes reading difficult

---

## 8. Libraries

Use CSS transitions when they are sufficient.

Use Motion, GSAP, Lenis, React Bits or Magic UI when they provide
meaningful value.

Do not add a library for a simple transition that CSS can handle.

Do not use multiple animation libraries unnecessarily.

---

## 9. Performance

Prefer animation properties that are efficient when possible.

Be cautious with:

- layout-triggering animation
- large blur effects
- heavy canvas effects
- continuous JavaScript animation
- large numbers of animated elements

Test animation on lower-powered devices when practical.

---

## 10. Reduced Motion

Respect:

`prefers-reduced-motion`

Provide an appropriately simplified experience.

Do not merely disable CSS while leaving broken transitions or hidden
content.

---

## 11. Client-Specific Motion

Motion should match the client.

Examples:

A medical clinic may benefit from:

- calm transitions
- subtle reveals
- soft movement

A motorcycle business may support:

- stronger directional movement
- sharper transitions
- more energetic interaction

A luxury interior designer may support:

- editorial image reveals
- slow transitions
- sophisticated movement

Do not use the same motion language for every client.

---

## 12. Final Motion Review

Ask:

- Does this animation have a purpose?
- Does it reinforce the design?
- Is it distracting?
- Does it delay interaction?
- Is it performant?
- Does it fit the brand?
- Does it work on mobile?
- Does reduced motion work?
- Would the interface be better without it?

If removing an animation improves the experience, remove it.