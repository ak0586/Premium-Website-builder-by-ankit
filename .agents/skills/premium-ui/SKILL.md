---
name: premium-ui
description: Guides premium visual interface design with intentional hierarchy, typography, composition, restrained motion, client-specific visual identity, and strong visual refinement while avoiding generic AI-generated aesthetics.
---

# Premium UI Skill


## Purpose

Use this skill when designing or improving the visual interface of a website.

The objective is premium visual quality without creating a recognizable "AI-generated website" aesthetic.

## Core Principle

Premium quality comes from:

- hierarchy
- typography
- composition
- spacing
- color
- imagery
- interaction
- consistency
- restraint
- refinement

Do not confuse visual complexity with premium quality.

## Avoid Generic AI Aesthetics

Do not automatically use:

- neon gradients
- purple-blue SaaS gradients
- excessive glassmorphism
- excessive rounded cards
- giant gradient text
- excessive floating blobs
- repetitive card grids
- excessive shadows
- identical section structures
- decorative animations everywhere

These may be used only when justified by the creative direction.

## Visual Hierarchy

Every page should have clear:

- primary message
- secondary information
- supporting information
- primary CTA
- secondary actions

Not every element should compete for attention.

## Typography

Choose typography according to:

- industry
- audience
- personality
- brand
- geography
- readability
- content volume

Do not default to Inter.

Consider combinations of:

- display serif + neutral sans
- humanist sans
- geometric sans
- editorial serif
- condensed display
- expressive display type

Typography should contribute to identity.

## Color

Do not use a universal palette.

Choose color based on:

- industry
- emotional positioning
- audience
- brand
- cultural context
- accessibility
- conversion

Use accent colors intentionally.

Do not make every section colorful.

## Layout

Use composition deliberately.

Possible structures include:

- editorial
- asymmetric
- split-screen
- centered
- immersive
- modular
- minimal
- image-led
- typography-led

Do not repeat the same card-grid layout throughout the page.

## Components

Use components to create consistency, not sameness.

Good candidates for reuse:

- buttons
- inputs
- navigation primitives
- dialogs
- tabs
- accordions
- tooltips
- form primitives

Customize visual treatment to the client.

## shadcn/ui

Use shadcn/ui for reliable UI primitives when appropriate.

Do not allow default shadcn styling to determine the client's visual identity.

Customize:

- radius
- typography
- spacing
- borders
- shadows
- colors
- states

## React Bits

Use React Bits selectively for:

- text effects
- interesting interactions
- visual transitions
- distinctive interface moments

Do not add effects merely because they are available.

## Magic UI

Use Magic UI selectively for:

- polished visual effects
- subtle animated elements
- premium interaction details

Do not turn the entire website into a Magic UI showcase.

## Icons

Prefer a coherent icon family.

Use Lucide or another appropriate icon system when needed.

Do not mix unrelated icon styles.

## Buttons

Buttons should have:

- clear hierarchy
- obvious affordance
- appropriate size
- hover state
- focus state
- disabled state when relevant

Primary CTA should visually stand out without looking aggressive.

## Cards

Cards should only exist when they improve information organization.

Do not put every piece of content inside a card.

Consider:

- open layouts
- dividers
- whitespace
- typography
- image composition

before creating another card.

## AI Concierge Widget Design (Bespoke Standard)

The conversational assistant widget must feel like an organic, custom-built extension of the client's visual identity:

- **Bespoke Styling**: Typography, container framing, color tokens, and border radii must match the client's design system. It must never look like an off-the-shelf, generic third-party chat plugin.
- **Brand-Derived Avatar**: The animated avatar (idle, listening, thinking, speaking) must visually embody the specific business character (e.g. clinical precision for a healthcare studio, artisanal warmth for a barber or cafe). Use lightweight vector animation (SVG, Lottie, or Rive).
- **Mobile Harmony**: Positioned and sized to preserve generous clearance around mobile primary CTAs and navigation controls.
- See canonical reference: [design-system/chatbot-widget.md](file:///e:/clients-websites/Premium-Website-builder-by-ankit/design-system/chatbot-widget.md).

## Luxury Healthcare & 3D Spatial Experiences (Opt-In Exception Path)

> [!NOTE]
> Applies strictly when the 3D gating criteria in [.agents/rules/01-premium-design.md](file:///e:/clients-websites/Premium-Website-builder-by-ankit/.agents/rules/01-premium-design.md) are met. For standard clients, prioritize 2D craft and lightweight depth.

When designing flagship healthcare, aesthetic, or architectural experiences that justify real-time 3D:

### The "Luxury Healthcare" Standard
- Elevate the environment to feel like a high-end luxury wellness brand rather than a sterile clinic.
- Combine warm off-white / ivory backgrounds (`#FAFAF7`), champagne accents, soft studio shadows, and restrained dark typography.
- Communicate three core values: **PRECISION**, **TRUST**, and **CONFIDENCE**.

### Physical Material Authenticity
- Render biological surfaces (enamel, tissue, skin) with anatomical realism, subsurface light transmission, perikymata micro-grooves, and natural clearcoat moisture.
- Avoid the artificial "plastic CGI" look.
- Never use cartoon tooth icons, floating toothbrushes, dental emojis, or neon holographic effects.

### Negative Space & Typography Integration
- Structure heroes with a 40/60 balance: the 3D subject occupies ~40% of the screen, leaving generous negative space for editorial typography and CTAs.
- The typography must feel physically integrated into the studio environment rather than layered on top.

---

## Final UI Review

Ask:

- Does this look intentionally designed?
- Does the typography have personality?
- Is the hierarchy obvious?
- Is the layout memorable?
- Are decorative elements necessary?
- Does the UI feel specific to this client?
- Does the AI concierge widget feel bespoke to the client rather than an off-the-shelf plugin?
- Does the experience default to high-craft 2D with lightweight depth, or was 3D uncritically reached for?
- Does anything look like a default AI template?

Fix weak areas before adding more decoration.