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