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

---

## 8. Navigation

Navigation should remain:

- clear
- accessible
- predictable
- responsive

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

## 15. Cinematic 3D Hero & Interactive Canvas Components

For experiences incorporating WebGL / Three.js 3D environments:

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
- On mobile devices, utilize simplified camera paths and touch-damped orbital shifts to maintain a silky 60fps frame rate.
- Always clean up WebGL contexts, geometries, materials, and animation frame IDs on unmount.

---

## 16. Final Component Review

Ask:

- Does this component need to exist?
- Is it reusable?
- Is it accessible?
- Is it responsive?
- Is it visually appropriate?
- Is it unnecessarily complex?
- Does it fit the client's design system?
- Is the component library influencing the design too much?