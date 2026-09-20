---
name: new-client
description: Guides the creation of a new client website from business understanding and research through creative direction, information architecture, design system, implementation, responsive refinement, visual QA, and final QA.
---

# New Client Website Skill


## Purpose

Use this skill when starting a new client website.

The goal is to create a premium, client-specific website rather than applying a generic template.

## Workflow

Always follow this sequence:

1. Understand the client
2. Understand the target audience
3. Understand the business model
4. Research the market when useful
5. Research relevant competitors
6. Define the website's primary conversion goal
7. Define creative direction (2D-first craft default; 3D strictly gated)
8. Derive the category-specific motion concept
9. Define AI concierge widget (personality, avatar, integration mode)
10. Define information architecture
11. Define design system
12. Select appropriate technologies
13. Implement
14. Refine interactions and motion
15. Test responsive behavior (including throttled budget mobile hardware)
16. Perform visual QA
17. Perform technical QA
18. Perform final self-critique

Do not skip directly from a business description to coding.

## Prospecting Relationship

Prospecting is a separate workflow.

If the user has not yet selected a client and asks to find potential clients, use the `prospecting` skill first.

Do not mix prospect discovery with client implementation.

Once a prospect is explicitly selected, switch to the new-client workflow.

## Client Understanding

Before implementation, determine when possible:

- business type
- location
- target customers
- customer intent
- primary services/products
- differentiators
- trust requirements
- desired action
- brand personality
- local vs international audience
- existing brand assets
- existing website
- social presence
- competitors

Never invent missing factual information.

Use placeholders when real information is unavailable.

## Research

Use web research when it materially improves the result.

Research should help understand:

- competitor positioning
- industry conventions
- customer expectations
- visual patterns
- service presentation
- conversion patterns
- local market expectations

Research should inform decisions, not cause imitation.

Never copy competitor layouts, branding, wording, imagery, or distinctive visual identity.

## Creative Direction

Before coding, establish:

- visual personality
- typography direction
- color direction
- layout character
- imagery direction
- interaction personality
- motion personality
- category-specific motion concept
- content hierarchy

The design should have a clear reason for existing.

## Category-Specific Motion Concept (Required)

Motion personality alone (calm, energetic, luxurious, etc.) is not
sufficient. Before implementation, derive a motion concept specific to
the client's actual industry using the six-question method in
`design-system/category-motion.md`:

1. What physical or conceptual characteristics define this business?
2. What visual metaphors naturally emerge from those characteristics?
3. Which of those metaphors can become motion?
4. Which motion would reinforce the brand?
5. Which motion would improve storytelling or comprehension?
6. Which motion would simply be decoration, and should therefore be rejected?

Consult the industry motion bank in `design-system/category-motion.md`
for inspiration only — never copy an entry directly. Two clients in
the same industry must receive different executions, driven by their
specific brand, positioning, audience, and content.

Record the resulting motion concept in the client design brief
(`docs/client-design-brief-template.md`, Section 10, Motion Concept
Derivation) before major implementation begins.

Reject candidate motion ideas that are decoration with no relationship
to the business, even if they look technically impressive. Reject
literal or gimmicky interpretations (cartoon objects, things flying
across the screen, motion with no metaphorical connection to the
client) — see `design-system/category-motion.md` Section 7 for
examples.

## AI Concierge Widget & Chatbot Presentation Constraints (Required)

Every client website must include an AI concierge slot for interactive Q&A and appointment booking.
See canonical specification in [design-system/chatbot-widget.md](../../../design-system/chatbot-widget.md):

- Derive the assistant's visual identity, avatar character, and motion personality directly from the client's brand.
- **Launcher button presentation**: Display a lovely, brand-matched animated avatar accompanied simply by the name **Ushera** (clean, compact luxury pill, e.g. `<ConciergeAvatar size={32} /> Ushera`). Never use verbose text like "Ask & Book with Ushera".
- **Strict single-line navbar**: Every navigation button, status badge, and CTA in the navbar must remain strictly on a single line (`white-space: nowrap; flex-shrink: 0;`), never wrapping words across multiple lines. Never duplicate "Ask Ushera & Book" in center links when the right CTA button already triggers booking/Ushera.
- **No redundant static consultation form**: Because Ushera handles inquiries, scheduling, pricing, and intake via interactive chat and voice, **do NOT build a separate static consultation form** or two-column form layout. The consultation section should instead feature direct clinic contact details (phone, hospital address, timings) and a direct button triggering Ushera.
- **Button restraint on cards**: Do not sprinkle repetitive "Ask & Book with Ushera" buttons across individual service cards or carousel slides.
- Use lightweight vector animation (SVG animation, Lottie, or Rive) for idle, listening, thinking, and speaking avatar states—never heavy raw GIFs.
- Support dual modes: text chat and push-to-talk voice with live transcript.
- Implement behind a clean, pluggable adapter interface: runs out of the box in placeholder/demo mode (with realistic scripted responses and direct WhatsApp/phone fallback links), ready to connect to any external AI Receptionist SaaS backend.
- Ensure the widget is asynchronously loaded, does not block FCP/LCP, and respects mobile CTA clearance.

## Design System

Define appropriate:

- colors
- typography
- spacing
- container widths
- border radius
- borders
- shadows
- buttons
- cards
- forms
- navigation
- section patterns
- responsive behavior
- motion principles

Do not assume the same design system should be visually reused for every client.

Reuse architecture and quality standards, not visual identity.

## Technology

Choose the simplest appropriate stack.

Must include:

- React + Vite
- Three.js (mandatory for bespoke, unique 3D animation mapped to client specialization)
- Motion (Framer Motion)
- GSAP + ScrollTrigger
- Lenis (smooth momentum scroll)
- CSS Modules / Vanilla CSS / Tailwind (as appropriate)
- React Bits / Magic UI (selective signature moments)
- Lottie / Rive (for vector bot avatars and lightweight spot animations)

Do not add libraries without a clear reason.

## Implementation

Build the highest-value areas first:

1. Header/navigation (strictly single-line items, no wrapped text, clean CTA)
2. Hero (mandatory bespoke Three.js 3D animation + editorial typography and photography)
3. Primary conversion path (floating Ushera widget + hero CTA + navbar CTA)
4. Interactive features (3D cylinder treatment carousel with bespoke SVGs, smooth before/after comparison slider)
5. Core services/content (clean cards without repetitive buttons)
6. Consultation & Contact (reception phone, hospital address, operating hours, direct Ushera trigger; NO redundant static form)
7. Trust sections & proof
8. Supporting sections
9. Footer

Do not spend excessive effort on decorative elements before the core experience is strong.

## Agency Attribution

When creating a new client website, check the client design brief for the required Kyvronix Technologies attribution.(website link: https://kyvronix.com)

If attribution is enabled, implement it primarily in the footer and keep it visually subordinate to the client's brand.

Use the approved wording and placement defined by the client project.

Do not introduce prominent Kyvronix branding unless explicitly required.

## Mandatory Full-Site Motion

Every new client website must be animated throughout the experience.

Follow the **2D-first craft default hierarchy**: beautiful 2D craft
(photography, typography, vector illustration, SVG) $\to$ purposeful motion
(scroll reveals, image movement, text animations, hover feedback) $\to$
lightweight depth (parallax, perspective, layering, scale, blur). WebGL and
3D scenes are strictly opt-in exception moments requiring explicit justification.

During creative direction, define the project's motion personality
AND derive its category-specific motion concept (see above) before
implementation.

During implementation, establish motion across appropriate layers:

- page load
- navigation
- hero (default 2D-first craft + lightweight depth)
- content sections
- images
- components
- interactions
- scrolling
- transitions
- footer

Motion must feel smooth and cohesive rather than consisting of isolated animation effects.

Do not use an identical animation recipe across projects.

The client's industry, audience, brand personality, positioning, content, and visual direction should determine the motion language.

Before completion, perform a dedicated motion review of the entire website and verify smoothness (60fps on throttled budget mobile hardware), consistency, responsiveness, performance, reduced-motion behavior, and that the motion concept is specific to this client rather than generic to its industry.

## Responsive Design

Treat mobile as a first-class experience. Low-end device performance (budget ₹8k–15k Android phones) is a foundational design constraint.

Verify:

- navigation
- typography
- spacing
- buttons
- forms
- images
- section composition
- horizontal overflow
- touch interactions
- AI concierge widget clearance (never obstructing primary CTA or nav)

Do not merely shrink the desktop layout.

## Motion

Use motion only when it improves:

- hierarchy
- orientation
- feedback
- storytelling
- perceived quality

Avoid motion that competes with content.

Respect reduced-motion preferences.

## Verification

When possible, inspect the rendered website across multiple simulated device profiles.

Do not claim visual QA was completed without actually inspecting the result.

## Completion

Before considering the project complete:

- visual hierarchy is strong
- typography feels intentional
- layout feels designed
- mobile experience is polished on simulated throttled device (4x CPU slowdown)
- interactions feel natural
- motion defaults to 2D-first craft + lightweight depth (3D strictly justified if used)
- the motion concept is specific to this client's industry and brand, not a generic recipe
- AI concierge widget is present, on-brand, functional (or cleanly placeholder-stubbed with fallback contact), and does not regress Core Web Vitals
- no obvious AI-generated visual patterns remain
- content is factual
- no secrets are exposed
- build succeeds
- important links work
- console is clean
- SEO basics exist
- accessibility basics are addressed
