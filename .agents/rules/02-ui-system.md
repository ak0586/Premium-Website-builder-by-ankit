---
trigger: always_on
---

# UI System Rules

## Purpose

Create a coherent, accessible and maintainable interface while
preserving each client's unique visual identity.

UI libraries are implementation resources.

They must never dictate the client's design.

---

## 1. Preferred UI Resources

Preferred resources include:

- shadcn/ui
- React Bits
- Magic UI
- Motion
- GSAP
- Lenis
- Lucide icons
- Lottie / Rive (for lightweight vector animation & bot avatars)

Use only what is appropriate.

Do not install libraries simply because they are available.

---

## 2. shadcn/ui

Use shadcn/ui primarily for:

- buttons
- inputs
- forms
- dialogs
- sheets
- menus
- navigation
- tabs
- accordions
- accessible primitives

Customize the implementation to match the client's design system.

Do not allow default shadcn styling to become the website's identity.

---

## 3. React Bits

Use React Bits selectively for:

- text effects
- hover interactions
- visual transitions
- advanced interactions
- animation patterns

Do not turn the website into an animation showcase.

Every selected effect must have a reason.

---

## 4. Magic UI

Use Magic UI selectively for:

- animated components
- marquees
- number animations
- backgrounds
- visual accents
- interaction patterns

Customize components to match the client.

Do not reproduce Magic UI demo aesthetics blindly.

---

## 5. Component Selection

Before using a component, consider:

1. Does it solve a real UX problem?
2. Does it fit the visual direction?
3. Can it be customized?
4. Is the dependency justified?
5. Does it affect performance?
6. Does it create unnecessary complexity?

Prefer existing project components when they already solve the problem.

---

## 6. Component Architecture

Components should have clear responsibilities.

Prefer:

- composable components
- focused components
- predictable props
- clear naming
- accessible states
- reusable variants

Avoid:

- giant components
- unnecessary abstraction
- deeply nested prop chains
- generic "universal" components
- abstraction before reuse is demonstrated

---

## 7. Buttons

Buttons should communicate hierarchy.

Use appropriate levels:

- primary
- secondary
- tertiary
- destructive where appropriate

Do not make every action look like the primary CTA.

Buttons must have:

- clear labels
- hover states
- focus states
- disabled states where relevant
- appropriate touch targets

---

## 8. Cards

Cards should group content when grouping improves comprehension.

Do not put every piece of content into a card.

Avoid:

- excessive rounded containers
- unnecessary shadows
- card grids everywhere

Use alternative compositions when they communicate information better.

---

## 9. Forms

Forms must prioritize:

- clear labels
- useful field grouping
- validation
- error states
- focus states
- accessible controls
- clear submission feedback
- mobile usability

Do not hide important labels behind placeholders.

---

## 10. Navigation

Navigation should reflect the information architecture.

Keep navigation:

- clear
- predictable
- accessible
- responsive

Do not add unnecessary menu items.

Mobile navigation should be designed intentionally rather than simply
collapsed from desktop.

---

## 11. AI Concierge Widget (Chat + Voice)

Every client website must provide a conversational assistant slot (chat + push-to-talk voice):

- Functions as a primary conversion path for real-time Q&A and appointment booking.
- Incorporates a brand-styled vector animated avatar (idle, listening, thinking, speaking states) using SVG, Lottie, or Rive—never heavy GIFs.
- Pluggable architecture: functions immediately in standalone placeholder/demo mode (with scripted mock responses and WhatsApp/tel direct fallback) or connects seamlessly to an external multi-tenant AI Receptionist SaaS backend.
- Non-blocking, asynchronously loaded, keyboard-accessible, and strictly clear of mobile CTA and navigation touch targets.

See canonical reference: [design-system/chatbot-widget.md](../../design-system/chatbot-widget.md).

---

## 12. Icons

Use icons consistently.

Prefer a single coherent icon style.

Do not use icons merely as decoration.

Icon-only controls must have accessible names.

---

## 13. Visual Consistency

Maintain consistency in:

- spacing
- typography
- control height
- radius
- borders
- shadows
- states
- interaction behavior

But do not confuse consistency with repetition.

Different content types may require different compositions.

---

## 14. Design Tokens

Whenever possible, centralize:

- colors
- typography
- spacing
- radius
- shadows
- motion values
- breakpoints

Avoid scattering arbitrary values throughout the codebase.

Refer to:

`design-system/`

for the project's deeper design system.

---

## 15. Premium Quality

Premium UI should come from:

- composition
- hierarchy
- typography
- spacing
- interaction
- content
- consistency
- restraint

Do not attempt to make a UI premium simply by adding:

- gradients
- shadows
- glass effects
- animation
- rounded corners

---

## 16. Final UI Review

Before completing a major UI component, ask:

- Is the hierarchy clear?
- Is the component necessary?
- Does it fit the client?
- Does it feel generic?
- Is it accessible?
- Is it responsive?
- Are states handled?
- Is the component unnecessarily complex?
- Can anything be simplified?
- Is the AI concierge widget present, on-brand, performant, and mobile-friendly without blocking primary CTAs?