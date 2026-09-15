# Premium UI Stack

## Primary Required Animation Stack

Every client website built in this system MUST use the following four
technologies as its animation foundation:

| Technology | Role | Install |
|------------|------|---------|
| **Motion (Framer Motion)** | Scroll-triggered reveals, clip-path wipes, parallax, AnimatePresence | `npm install framer-motion` |
| **GSAP** | Timeline choreography, ScrollTrigger, counter animations, word splits | `npm install gsap` |
| **React Bits** | Premium text effects, magnetic interactions, count-up animations | `npm install @gsap/react` or inline |
| **CSS / SVG Animations** | Avatar states, ambient marks, hover transitions, link underlines | Native — no install |
| **Lenis** | Momentum smooth scroll (async loaded after LCP) | `npm install lenis` |

These are **required by default**. Only remove a technology if the project
genuinely does not require it, and document the reason in the design brief.

> [!IMPORTANT]
> Do not reduce the stack merely to minimize setup time. The animation craft
> quality enabled by this stack is part of the premium standard.

---

## Standard Setup

```bash
npm install framer-motion gsap lenis lucide-react
```

For GSAP ScrollTrigger (used for advanced scroll-driven storytelling):

```js
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger)
```

For Lenis (load after LCP — async import in `useEffect`):

```js
useEffect(() => {
  let lenis
  import('lenis').then(({ default: Lenis }) => {
    lenis = new Lenis({ duration: 1.2, easing: t => Math.min(1, 1.001 - Math.pow(2, -10 * t)) })
    function raf(time) { lenis.raf(time); requestAnimationFrame(raf) }
    requestAnimationFrame(raf)
  }).catch(() => {}) // fail silently — smooth scroll is progressive enhancement
  return () => lenis?.destroy()
}, [])
```

---

## Additional UI Resources

Use these selectively when they provide genuine value beyond the required stack:

- **shadcn/ui** — accessible form primitives, dialogs, sheets, menus
- **Magic UI** — marquees, number animations, animated backgrounds
- **Lucide** — icon set (consistent, lightweight)
- **Lottie / Rive** — complex vector animations (AI avatar if CSS SVG is insufficient, brand spot animations)
- **Three.js / WebGL** — exception path only, gated by `.agents/rules/01-premium-design.md`

---

## Where to Use Each Technology

See `design-system/motion.md` Section 2c (Primary Technique Library) for
concrete, copy-reference code patterns for every animation the system requires.

---

## Premium Quality Comes From

Libraries accelerate implementation. They do not replace design decisions.

Premium quality comes from:

- creative direction
- typography
- color
- composition
- imagery
- spacing
- hierarchy
- interaction
- motion
- responsive behavior
- accessibility
- performance
- content
- refinement

A website does NOT become premium merely by installing animation libraries.

**The canon reference implementation** demonstrating every required technique
is `e:\clients-websites\devaki-dental-v2\`.