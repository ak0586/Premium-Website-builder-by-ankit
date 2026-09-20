# Component Design System

## 1. Components Serve the Design

Components should help maintain consistency without forcing every
client into the same visual identity.

---

## 2. Reuse Architecture, Not Appearance

Reusable:

- behavior
- accessibility
- logic
- layout primitives
- utilities
- engineering patterns

Client-specific:

- colors
- typography
- borders
- radius
- shadows
- imagery
- animation
- composition

---

## 3. Component Responsibilities

A component should have a clear responsibility.

Avoid giant components containing unrelated behavior.

---

## 4. Component States

Interactive components should consider:

- default
- hover
- focus
- active
- disabled
- loading
- error
- success

Only implement states that are relevant to the component.

---

## 5. Buttons

Buttons should establish hierarchy.

Possible levels:

- primary
- secondary
- tertiary
- destructive

Do not make every action equally prominent.

---

## 6. Cards

Use cards when grouping content improves comprehension.

Do not use cards for everything.

Alternatives include:

- lists
- editorial layouts
- dividers
- open compositions
- grids without card containers
- image-led layouts

### Button Restraint on Cards
Do NOT add repetitive "Ask & Book with Ushera" or "Book Consultation" buttons to individual service cards, diagnostic cards, or carousel slides. Cards should focus on clinical explanation, procedural context, and bespoke medical SVG iconography. Reserve conversion buttons for the primary hero, header navbar, persistent floating Ushera launcher, and the appointment section.

---

## 7. Forms

Forms should be:

- clear
- accessible
- responsive
- easy to complete

Provide:

- labels
- validation
- errors
- feedback
- appropriate CTA hierarchy

### Consultation Form Omission Rule (When Ushera is Present)
When the website features the Ushera AI concierge assistant, **do NOT implement a redundant static consultation form** or cumbersome two-column form layout. Ushera directly handles patient questions, scheduling intake, procedure triage, and booking requests via interactive chat and voice. 

Instead of a static form, the appointment/contact section should feature:
- Direct clinic telephone line (`tel:`)
- Verified physical facility / hospital address & directions
- Operating days & hours
- A prominent, elegant button triggering Ushera to guide the booking

---

## 8. Navigation

Navigation should remain:

- clear
- accessible
- predictable
- responsive

### Strict Single-Line Navigation Constraint
- Every navigation link, status indicator badge, and call-to-action button in the navbar **must remain strictly on a single line** (`white-space: nowrap; flex-shrink: 0;`).
- Multi-word labels (such as `Diagnostic Compass`, `Hospital Standards`, `The Life Plus Hospital`, `Book Appointment`) must never wrap text across multiple lines.
- Container padding, flex gaps, and viewport media queries must ensure adequate breathing room without compressing elements into multi-line breaks.

### Navigation Link Deduplication
- Do not include an "Ask Ushera & Book" link in the center navigation list when the far-right CTA button already triggers booking or opens the Ushera concierge.
- Center navigation is strictly reserved for primary content anchors (e.g. Rejuvenation, Diagnostic Compass, Standards, Doctor Profile).

Mobile navigation should receive intentional design treatment.

---

## 9. Icons

Use icons consistently.

Prefer one coherent icon family.

Do not use icons merely as decoration.

---

## 10. Component Libraries

Use:

- shadcn/ui
- React Bits
- Magic UI

selectively.

Customize components to match the client's design system.

Never allow the default visual style of a library to determine the
client's identity.

---

## 11. Component Variants

Use variants when they represent meaningful differences.

Do not create variants for every tiny visual difference.

---

## 12. Component Naming

Use names that describe purpose.

Prefer:

- `PrimaryButton`
- `ServiceCard`
- `BookingForm`
- `Testimonial`
- `SectionHeading`

over vague names such as:

- `Box`
- `Thing`
- `Container2`
- `FancyCard`

---

## 13. Responsive Components

Components must remain usable across screen sizes.

Do not rely on fixed dimensions that break responsive layouts.

---

## 14. Accessibility

Interactive components must provide:

- semantic elements
- keyboard support
- focus states
- accessible labels
- appropriate roles only when necessary

Prefer native HTML behavior where possible.

---

## 15. Default Lightweight 2D Hero Pattern (Standard)

For most premium local businesses, the standard hero is a lightweight,
motion-rich 2D composition that delivers immediate visual elegance and
instant performance across mobile devices.

### Architecture: Layered 2D Craft + Motion
- **Foreground Editorial Layer (`z-20`)**: High-contrast, beautifully set
  typography, trust badges/status pills, and the primary conversion CTA in a
  semantic DOM container.
- **Atmospheric & Depth Layer (`z-10`)**: Subtle radial gradients, soft blurred
  accent shapes, or delicate SVG vector lines creating visual depth without
  a real z-axis or WebGL overhead.
- **Imagery Layer (`z-0`)**: High-resolution photography, bespoke vector
  illustrations, or layered composite cutouts. Foreground and background image
  elements move at subtly different scroll rates (parallax) or respond with
  gentle scale-on-hover / Ken-Burns transitions.
- **Motion Polish**: CSS transforms (`translate3d`, `scale`) and `opacity`
  for entrance reveals; subtle hover feedback on interactive triggers; smooth
  scroll-driven parallax via `requestAnimationFrame` or passive scroll listeners.

### Benefits
- Zero WebGL startup latency or GPU lockup on budget mobile devices.
- Rock-solid Core Web Vitals (LCP < 2.0s even on throttled 4G connections).
- Seamless responsiveness and full cross-browser rendering fidelity.

---

## 16. Cinematic 3D Hero & Interactive Canvas (Opt-In Exception Path)

> [!IMPORTANT]
> **Exception Path Only**: 3D/WebGL heroes are reserved strictly for rare
> projects where the industry genuinely demands it (e.g. luxury aesthetic
> medicine, bespoke industrial design), budget permits thorough engineering/QA,
> and low-end mobile performance will NOT be compromised. See gating criteria
> in [.agents/rules/01-premium-design.md](../.agents/rules/01-premium-design.md).

For projects meeting these gating criteria:

### Architecture: Canvas + Layered DOM
- The WebGL Canvas should sit as a responsive, hardware-accelerated viewport layer (`z-0`).
- Editorial typography, status pills, and primary CTAs live in a pointer-events-managed semantic DOM layer (`z-20`).
- Use atmospheric gradient overlays (`z-10`) to softly feather 3D scene edges into the negative space of the page, ensuring text readability without heavy cards.

### Layout & Composition
- Maintain a **40/60 visual proportion**: the 3D subject occupies approximately 40% of the screen (typically right or center-right), leaving generous negative space for the primary headline and conversion path.
- The headline and CTA must feel physically integrated into the studio lighting environment rather than slapped on top.

### Responsive Rigs & Mobile Optimization
- Adjust camera field of view and translation vectors responsively.
- On desktop, enable interactive raycasting (cursor parallax and diagnostic contour highlights).
- On mobile devices, utilize simplified camera paths and touch-damped orbital shifts to maintain a silky 60fps frame rate, or gracefully fallback to a high-fidelity 2D still if GPU budget is tight.
- Always clean up WebGL contexts, geometries, materials, and animation frame IDs on unmount.

---

## 17. AI Concierge Widget (Chat + Voice)

Every client website includes a persistent, on-brand conversational assistant
slot designed as a core conversion path for Q&A and appointment booking.

### Canonical Specification
For full architecture, pluggable adapter design, animated vector avatar
specifications, accessibility, and fallback rules, refer to the canonical
document:

- [design-system/chatbot-widget.md](chatbot-widget.md)

### Key Component Traits
- **Dual Mode**: Seamlessly supports text chat and push-to-talk voice with live
  transcript fallback.
- **Animated Bot Presence**: Uses brand-styled lightweight vector animation (SVG,
  Lottie, or Rive) for idle/listening/thinking/speaking states—never heavy GIFs.
- **Pluggable Architecture**: Works out of the box in placeholder/demo mode
  (mock responses, direct WhatsApp/phone fallback) and adapts cleanly to any
  live AI receptionist SaaS backend without refactoring UI code.
- **Mobile Clearance**: Placed unobtrusively in a bottom viewport anchor, carefully
  spaced so it never obstructs primary CTA buttons or nav bars.

---

## 18. Final Component Review

Ask:

- Does this component need to exist?
- Is it reusable?
- Is it accessible?
- Is it responsive?
- Is it visually appropriate?
- Is it unnecessarily complex?
- Does it fit the client's design system?
- Is the component library influencing the design too much?
- Does the hero default to high-craft 2D, or has 3D been explicitly justified?
- Is the AI Concierge widget present, on-brand, performant, and mobile-friendly?