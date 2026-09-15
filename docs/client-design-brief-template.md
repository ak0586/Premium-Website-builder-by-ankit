# Client Design Brief

> Use this document for every new client website.
>
> This is the project's design and product contract. It should be completed before significant implementation begins and updated when major design decisions change.

---

## 1. Client Overview

### Business Name

[Real business name]

### Business Type

[Clinic / Barber / Bike Repair / Restaurant / SaaS / etc.]

### Location

[City, Country]

### Target Market

[Local / regional / national / international]

### Website Type

[Marketing website / service website / booking website / ecommerce / portfolio / etc.]

---

## 2. Business Understanding

### What the Business Does

[Short factual description]

### Primary Services / Products

* [Service/product]
* [Service/product]
* [Service/product]

### Business Differentiators

Only include verified differentiators.

* [Differentiator]
* [Differentiator]
* [Differentiator]

### Customer Problem

[What problem does the customer want solved?]

### Customer Intent

[What is the visitor most likely trying to accomplish?]

---

## 3. Audience

### Primary Audience

[Who is the most important visitor?]

### Secondary Audience

[Optional]

### Audience Expectations

Consider:

* trust
* speed
* convenience
* expertise
* affordability
* prestige
* reliability
* reassurance
* local familiarity
* visual quality

### Customer Psychology

What should the visitor feel?

* [Feeling]
* [Feeling]

What should the visitor believe after using the website?

* [Belief]
* [Belief]

---

## 4. Conversion Strategy

### Primary Conversion Goal

[Book appointment / Call / WhatsApp / Request quote / Buy / Visit location / Contact / etc.]

### Secondary Conversion Goal

[Optional]

### Primary CTA

[Exact CTA]

### Secondary CTA

[Exact CTA]

### Conversion Friction

What could prevent the user from taking action?

* [Problem]
* [Problem]
* [Problem]

### Trust Requirements

Potential trust signals:

* verified credentials
* real business information
* genuine testimonials
* real photos
* service details
* transparent pricing when available
* location
* opening hours
* contact information
* booking process
* guarantees when factually supported

Never invent trust signals.

---

# 5. Research

## Market Research

[Important findings]

## Competitor Research

### Competitor 1

[Name + URL]

**Strengths**

* [Finding]

**Weaknesses**

* [Finding]

**Opportunity**

[How our design can differentiate]

### Competitor 2

[Name + URL]

**Strengths**

* [Finding]

**Weaknesses**

* [Finding]

**Opportunity**

[How our design can differentiate]

### Competitor 3

[Name + URL]

**Strengths**

* [Finding]

**Weaknesses**

* [Finding]

**Opportunity**

[How our design can differentiate]

---

# 6. Creative Direction

## Design Personality

Choose descriptive words rather than generic terms such as "modern" alone.

Examples:

* editorial
* refined
* warm
* clinical
* sophisticated
* energetic
* technical
* rugged
* understated
* playful
* premium
* trustworthy
* human
* luxurious
* utilitarian

### Primary Personality

[Description]

### Secondary Personality

[Description]

### Overall Design Statement

> [One or two sentences describing what the website should feel like.]

---

# 7. Visual Identity

## Color Direction

### Primary Color

[Color + reason]

### Secondary Color

[Color + reason]

### Accent Color

[Color + reason]

### Background Strategy

[Description]

### Color Psychology

Explain why these colors fit:

* the business
* the audience
* the market
* the desired emotional response

Do not select colors merely because they are currently fashionable.

## Typography

### Display Typeface

[Typeface + reason]

### Body Typeface

[Typeface + reason]

### Supporting Typeface

[Optional]

### Typography Personality

[Description]

### Typography Rules

* [Rule]
* [Rule]

---

# 8. Layout & Composition

## Layout Character

Choose appropriate characteristics:

* editorial
* asymmetric
* centered
* modular
* immersive
* image-led
* typography-led
* minimal
* structured
* experimental

### Layout Direction

[Description]

### Container Strategy

[Description]

### Grid Strategy

[Description]

### Whitespace Strategy

[Description]

### Section Rhythm

[Description]

Avoid making every section follow the same visual structure.

---

# 9. Imagery

## Image Direction

[Photography / product photography / editorial / documentary / illustration / abstract / etc.]

### Image Personality

[Description]

### Image Treatment

[Full bleed / framed / cropped / monochrome / natural / etc.]

### Image Sources

Only use:

* client-provided assets
* properly licensed assets
* approved image sources
* generated imagery when appropriate

Do not imply that stock imagery represents the real business.

### Important Images

* [Image requirement]
* [Image requirement]

---

## 10. Motion Direction

### Motion Requirement

This project must use animation throughout the website.

The website should feel alive and fluid from initial load through navigation, scrolling, interaction, content transitions, and footer.

### Motion Concept Derivation

Complete this before defining Motion Personality below. See
`design-system/category-motion.md` for the full method and the
industry motion bank. Do not skip to a generic motion personality
without answering these six questions first.

1. What physical or conceptual characteristics define this business?

   [Answer]

2. What visual metaphors naturally emerge from those characteristics?

   [Answer]

3. Which of those metaphors can become motion?

   [Answer]

4. Which motion would reinforce the brand?

   [Answer]

5. Which motion would improve storytelling or comprehension?

   [Answer]

6. Which candidate motion ideas were rejected as pure decoration, and why?

   [Answer — this list should not be empty]

### Resulting Motion Concept

> [One or two sentences naming the specific, client-derived motion
> concept — not a generic tone. Would this concept transfer unchanged
> to a direct competitor in the same industry? It should not.]

### Motion Personality

- Motion personality:
- Motion intensity: Low / Moderate / High
- Overall motion character:
- Relationship to brand personality:

### Page-Level Motion

- Initial page-load behavior:
- Page transition behavior:
- Navigation transitions:
- Scroll behavior:
- Section transitions:

### Content Motion

- Hero reveal:
- Typography reveal:
- Image reveal:
- Section reveal:
- Stagger strategy:

### Interaction Motion

- Button behavior:
- Link behavior:
- Card behavior:
- Navigation behavior:
- Form behavior:
- Menu behavior:
- Other interactive states:

### Brand Motion

- Signature animation:
- Distinctive transition:
- Brand-specific interaction:

### Ambient Motion

- Background movement:
- Media movement:
- Decorative movement:
- Continuous animation, if any:

### Motion System

- Primary easing:
- Secondary easing:
- Typical duration:
- Entrance duration:
- Interaction duration:
- Stagger interval:
- Motion direction:
- Scale behavior:
- Opacity behavior:

### Animation Technology

- CSS / Motion / GSAP / Lenis / React Bits / Magic UI / Other:
- Reason for selection:

### Reduced Motion

- `prefers-reduced-motion` behavior:
- Non-essential motion removed:
- Essential state changes preserved:

### Performance

- Mobile animation strategy:
- GPU-friendly properties:
- Expensive effects intentionally avoided:
- Performance considerations:

### Animation Intentionally Avoided

Document motion patterns that do not fit this client's visual identity.

---

## 10b. AI Concierge / Ushera Chatbot (Required)

Every client website must include an on-brand AI concierge slot for interactive Q&A and appointment booking.
See canonical specification in [design-system/chatbot-widget.md](file:///e:/clients-websites/Premium-Website-builder-by-ankit/design-system/chatbot-widget.md).

- Enabled: Yes (Required by default)
- Name: Ushera
- Supported modes: Both Chat and Voice (Default)
- Launcher presentation: Compact luxury pill with lovely avatar + name "Ushera" only (NO verbose "Ask & Book with Ushera" text)
- Avatar style & visual personality: [Brand-derived description: colors, reticle/crest, motion style]
- Avatar technology: [SVG animation / Lottie / Rive — avoid raw GIFs]
- Primary booking flow: [Appointment booking / consultation request / callback request]
- Integration mode: [Placeholder/Demo mode (scripted + fallback) / Connected AI Receptionist SaaS backend]
- Fallback contact method: [Reception Phone `tel:` link / WhatsApp link]
- Placement: [Bottom-right anchor with explicit mobile CTA clearance]
- Navigation Bar Rule: All navbar items strictly single-line (`white-space: nowrap`), no duplicate Ushera links in center nav
- Consultation Form Rule: Redundant static consultation form omitted; Ushera serves as the interactive intake and scheduling concierge

## 10c. Bespoke Three.js 3D Animation & Signature Interactive Effects (Required)

Every client website must include a basic, smooth, unique 3D animation using Three.js tailored to the business specialization.

- 3D Specialization Concept: [Unique domain-specific 3D concept mapped to client's exact specialization — e.g. dermal matrix for dermatology, enamel prism for dental, joint kinematics for orthopedics, aerodynamic flow for auto]
- Three.js Implementation: [Geometry, particle system, lighting, camera parallax, 60fps optimization, resource disposal on unmount]
- 3D Cylinder / Carousel: [Bespoke SVG icons for each service card, horizontal drag/swipe navigation]
- Interactive Comparison Slider: [Hardware-accelerated before/after image slider with pointer capture]

---

# 11. Component Strategy

## Navigation

- Strict single-line rule: Every link, status pill, and CTA button has `white-space: nowrap` and `flex-shrink: 0`. No wrapping.
- Deduplication: Center links contain content anchors only. No duplicate "Ask Ushera & Book" in center links.

## Buttons

- Primary hero CTA, navbar CTA, contact section CTA, and floating Ushera launcher.
- Restraint: No repetitive "Ask & Book with Ushera" buttons on individual service cards.

## Cards

- Information-first: Procedure descriptions, doctor's approach, bespoke medical SVG icons. No repetitive booking buttons.

## Forms

- **Static consultation form omitted**: Replaced by direct reception phone, hospital address, hours, and direct Ushera booking trigger.

## Content Sections

[Description]

## AI Concierge Widget (Ushera)

[Specification of launcher (avatar + "Ushera"), chat/voice modal, animated vector avatar, and fallback booking path. See design-system/chatbot-widget.md]

## Icons

[Description]

## Special Components

* [Component]
* [Component]

Do not introduce components merely for decoration.

---

# 12. Information Architecture

## Primary Navigation

* [Page]
* [Page]
* [Page]

## Homepage Sections

1. [Section]
2. [Section]
3. [Section]
4. [Section]
5. [Section]

## Supporting Pages

* [Page]
* [Page]

### Content Priority

1. [Highest priority]
2. [Second priority]
3. [Third priority]

---

# 13. Responsive Strategy

## Mobile

[Important mobile decisions]

## Tablet

[Important tablet decisions]

## Desktop

[Important desktop decisions]

## Large Desktop

[Optional]

### Responsive Rules

* [Rule]
* [Rule]
* [Rule]

Mobile should be treated as a first-class experience rather than a reduced desktop layout.

---

# 14. Accessibility

### Requirements

* semantic HTML
* keyboard navigation
* visible focus states
* appropriate contrast
* accessible labels
* meaningful alt text
* logical heading hierarchy
* usable touch targets
* reduced-motion support

### Additional Requirements

* [Requirement]

---

# 15. Performance

### Image Strategy

[Description]

### Font Strategy

[Description]

### Animation Strategy

[Description]

### JavaScript Strategy

[Description]

### Third-Party Services

* [Service]
* [Service]

Only introduce third-party dependencies when their value justifies their cost.

---

# 16. SEO

### Page Title

[Draft]

### Meta Description

[Draft]

### Primary Search Intent

[Intent]

### Important Keywords

Use naturally and only when relevant.

* [Keyword]
* [Keyword]

### Local SEO

[If applicable]

### Structured Data

[If appropriate]

Never manufacture business information for SEO.

---

# 17. Content Rules

## Voice

[Professional / friendly / authoritative / conversational / etc.]

## Tone

[Description]

## Content Principles

* concise where possible
* specific rather than generic
* benefit-oriented
* easy to scan
* factually accurate
* appropriate for the audience

### Forbidden Without Verification

Do not invent:

* testimonials
* reviews
* awards
* certifications
* statistics
* prices
* addresses
* business history
* years of experience
* customer counts
* guarantees
* medical claims
* performance claims

---

# 18. Technology Decisions

### Framework

[Next.js / React / Vite / etc.]

### Styling

[Tailwind / CSS / etc.]

### UI Primitives

[shadcn/ui / custom / etc.]

### Motion

[Motion / GSAP / native CSS / etc.]

### Additional Libraries

* [Library]
* [Library]

### Why These Technologies?

[Short explanation]

Prefer the smallest appropriate technology stack.

---

# 19. Design References

### Reference 1

[URL]

**What to learn from it:**

[Specific aspect]

### Reference 2

[URL]

**What to learn from it:**

[Specific aspect]

### Reference 3

[URL]

**What to learn from it:**

[Specific aspect]

References are sources of inspiration and technique, not templates to copy.

---

# 20. Design Decisions

Record important decisions made during the project.

### Decision 1

**Decision:**

[Decision]

**Reason:**

[Reason]

**Alternative rejected:**

[Alternative]

### Decision 2

**Decision:**

[Decision]

**Reason:**

[Reason]

**Alternative rejected:**

[Alternative]

---

# 21. Anti-Patterns To Avoid

Based on this specific client, avoid:

* [Pattern]
* [Pattern]
* [Pattern]

General anti-patterns still apply:

* generic SaaS layouts
* excessive gradients
* unnecessary glassmorphism
* excessive rounded cards
* excessive shadows
* decorative animation without purpose
* repetitive card grids
* giant gradient headlines
* visual effects that compete with content
* a motion personality with no category-specific motion concept behind it
* a generic, off-brand chatbot bubble with no relationship to the client's identity
* an AI widget or unoptimized 3D/video asset that harms performance on budget mobile devices

---

# 22. Final Creative Test

Before implementation is considered complete, answer:

### Does this website feel specific to this client?

[Yes / No]

### Does the visual identity feel intentional?

[Yes / No]

### Does the design avoid generic AI aesthetics?

[Yes / No]

### Does the design support the business goal?

[Yes / No]

### Does the mobile experience feel deliberately designed?

[Yes / No]

### Is the content factually trustworthy?

[Yes / No]

### Is the level of visual complexity justified?

[Yes / No]

### Does the motion concept feel specific to this business, or would it work unchanged on a competitor?

[Answer]

### Were the motion and 3D decisions actually justified for this client, or reached for by default?

[Answer — confirm that 2D-first craft + lightweight depth was prioritized and any 3D moment met all gating criteria]

### What still feels generic?

[Answer]

### What should be improved?

[Answer]

---

# 23. Approval Gate

Before major implementation:

* [ ] Business understanding complete
* [ ] Audience defined
* [ ] Conversion goal defined
* [ ] Research completed where useful
* [ ] Creative direction defined
* [ ] Color direction defined
* [ ] Typography direction defined
* [ ] Layout direction defined
* [ ] Motion concept derived (Section 10, six-question method answered)
* [ ] Motion hierarchy verified (2D-first craft default; 3D gated and justified if used)
* [ ] Motion direction defined
* [ ] AI concierge widget defined (avatar, integration mode, fallback)
* [ ] Information architecture defined
* [ ] Technology selected
* [ ] Factual content verified or clearly marked as placeholder

Do not begin major implementation until the creative direction is sufficiently clear.

---

## Change Log

| Date   | Change        | Reason                 |
| ------ | ------------- | ---------------------- |
| [Date] | Initial brief | Project initialization |
|        |               |                        |
|        |               |                        |



## Agency Attribution

- Attribution required: Yes / No
- Attribution type: Built by / Built & managed by
- Attribution text:
- Kyvronix Technologies URL: https://kyvronix.com
- Client-approved placement:
- Client-specific requirements:
