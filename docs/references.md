# Design and UI References

The Premium Website Builder may use the following projects as
implementation and inspiration references.

## shadcn/ui

Official repository:
https://github.com/shadcn-ui/ui

Use for:
- accessible UI primitives
- buttons
- inputs
- forms
- dialogs
- navigation
- menus
- layout primitives

Do not allow shadcn/ui's default styling to determine the client's
visual identity.

Customize components to match the project's design system.

---

## React Bits

Official repository:
https://github.com/DavidHDev/react-bits

Use selectively for:
- interaction patterns
- animation ideas
- text effects
- hover interactions
- visual transitions
- advanced UI effects

Do not copy effects merely because they look impressive.

Every animation must support the client's design direction and UX.

---

## Magic UI

Official repository:
https://github.com/magicuidesign/magicui

Use selectively for:
- animated UI
- background effects
- marquees
- number animations
- visual accents
- premium interaction patterns

Do not allow Magic UI's visual style to become the default visual
identity of client websites.

---

## Cinematic 3D & Luxury Healthcare Benchmarks (Optional-Tier Exception Path)

> [!NOTE]
> **Optional-Tier References Only**: These benchmarks apply exclusively to the
> rare project that meets the explicit gating criteria in
> [.agents/rules/01-premium-design.md](file:///e:/clients-websites/Premium-Website-builder-by-ankit/.agents/rules/01-premium-design.md).
> They are NOT general baseline inspiration for every client. The standard default
> for local businesses is 2D-first craft + lightweight depth.

Award-winning benchmarks (Awwwards / CSS Design Awards inspirations such as LAVA Dental, Dentalux, Ori Scan, Apple Product Films):

Use as inspiration for:
- Macro camera journeys revealing microscopic material beauty
- Physical material authenticity (organic enamel translucency, clearcoat moisture sheen, perikymata ripples)
- Restrained, warm off-white / ivory studio environments
- Interactive diagnostic overlays (hairline contours, clinical telemetry)
- Seamless scroll-bound transitions morphing from physical objects into architectural treatment rooms
- Absolute prohibition of generic dental clichés (cartoon teeth, floating toothbrushes, neon blue sci-fi lasers)

# General Rule

These libraries are resources, not design systems for the client.

The client's own:
- brand
- audience
- industry
- market
- typography
- colors
- layout
- imagery
- motion language

must determine the final visual identity.

Prefer the smallest appropriate implementation.

Do not install or use a library component when native CSS/HTML or an
existing project component is sufficient.