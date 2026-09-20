---
trigger: always_on
---

# Performance and SEO Rules

## Performance

## 1. Performance Is Part of Design

A premium website should feel fast.

Do not prioritize visual effects at the expense of responsiveness.

---

## 1b. Performance Budget & Low-End Mobile Devices

Target clients are small local businesses whose customers browse primarily on
budget mobile devices (₹8k–15k Android phones) over variable mobile networks.

- **Core Web Vitals Under Throttling**: Target LCP < 2.5s, INP < 200ms, and CLS < 0.1
  under simulated mobile network and CPU throttling, not just on an unrestricted
  desktop dev machine.
- **High-Risk Technologies**:
  - **WebGL / 3D Canvas**: High GPU memory footprint, initial execution latency,
    and thermal throttling. Allowed strictly as an opt-in exception path (see gating
    criteria in [.agents/rules/01-premium-design.md](file:///e:/clients-websites/Premium-Website-builder-by-ankit/.agents/rules/01-premium-design.md)).
    When used, it must be lazy-loaded with an instant 2D fallback.
  - **Raw GIFs & Uncompressed Media**: GIFs have massive byte weights and lack hardware
    acceleration. Replace with lightweight vector animation (SVG, Lottie, Rive) or
    modern, compressed formats (WebP, AVIF).
- **AI Concierge Widget Asynchronous Loading**:
  - The AI concierge widget (chat + voice) must load asynchronously and deferred
    after primary content paint.
  - It must never block initial render, delay Largest Contentful Paint (LCP), or
    introduce layout shifts (CLS). See canonical specification in
    [design-system/chatbot-widget.md](file:///e:/clients-websites/Premium-Website-builder-by-ankit/design-system/chatbot-widget.md).
- **Mandatory Mobile Verification**: Test every project using simulated mobile
  device profiles with 4x CPU throttling and throttled network before final sign-off.

---

## 2. Dependencies

Avoid unnecessary dependencies.

Before adding a dependency ask:

- Is it necessary?
- Is there already a project solution?
- Can CSS/native browser APIs solve it?
- Does it add meaningful value?
- What is the maintenance cost?

---

## 3. Images

Optimize images for:

- dimensions
- format
- compression
- responsive usage
- loading behavior

Avoid unnecessarily huge images.

Use appropriate responsive image techniques.

---

## 3b. Video

When hero video is used (see `.agents/rules/01-premium-design.md`
§10b for when it fits creatively), it must meet the same performance
bar as any other hero treatment:

- Compress aggressively; serve WebM with an MP4 fallback.
- `muted autoplay loop playsinline` — never rely on unmuted autoplay,
  which browsers block anyway.
- Always set a `poster` frame so the perceived hero loads instantly,
  even before the video itself is ready.
- The video must never be, or block, the Largest Contentful Paint
  element. Treat the poster/first-frame as LCP-critical; load the
  actual video asset after.
- On low-end/low-bandwidth mobile, fall back to the static poster
  image or an equivalent photograph rather than forcing video
  playback — detect via `prefers-reduced-motion`, connection type
  (`navigator.connection.saveData` / `effectiveType`), or a simple
  viewport-width threshold.
- Keep the clip short and loopable (a few seconds) rather than a long
  file that inflates page weight for a background loop.

An unoptimized hero video that degrades Core Web Vitals or budget
mobile performance has failed the premium standard, regardless of how
good it looks on a fast connection.

---

## 4. Fonts

Avoid loading unnecessary font families and weights.

Prefer intentional font selection.

Do not load many fonts simply to experiment.

---

## 5. JavaScript

Avoid unnecessary client-side JavaScript.

Prefer:

- CSS
- semantic HTML
- server/static rendering where appropriate
- progressive enhancement

when they can solve the problem.

---

## 6. Animation Performance

Avoid expensive continuous animations.

Be cautious with:

- large blur effects
- canvas
- excessive DOM animation
- layout-triggering animation
- unnecessary JavaScript loops

---

## 7. Third-Party Services

Do not add third-party scripts without a reason.

Consider:

- performance
- privacy
- reliability
- maintenance
- client requirements

---

# SEO

## 8. Page Metadata

For public websites, provide appropriate:

- title
- meta description
- canonical URL where appropriate
- Open Graph metadata
- favicon

---

## 9. Semantic Structure

Use semantic HTML and appropriate heading hierarchy.

The page structure should communicate meaning.

---

## 10. URLs

Prefer clean, readable URLs.

Avoid unnecessary query parameters or complicated route structures.

---

## 11. Structured Data

Use appropriate structured data when it genuinely benefits the
website.

Do not fabricate structured-data values.

---

## 12. Sitemap and Robots

Provide:

- sitemap
- robots.txt

when appropriate for the project.

---

## 13. Local SEO

For local businesses, where appropriate consider:

- business name
- address
- phone
- service areas
- opening hours
- location information
- appropriate LocalBusiness structured data

Only use verified business information.

---

## 14. SEO Content

Do not keyword-stuff.

Do not create low-quality paragraphs merely to increase word count.

SEO content should remain useful to humans.

---

## 15. Performance and SEO Verification

Before completion:

- run production build
- check console errors
- check missing assets
- inspect loading behavior
- verify metadata
- verify important routes
- verify images
- verify sitemap/robots where applicable
- test on simulated low-end/throttled mobile device profile (4x CPU slowdown, Fast 3G/Slow 4G)
- verify AI concierge widget loads asynchronously and does not regress Core Web Vitals (LCP, INP, CLS)
- confirm any 3D/WebGL moment passes gating criteria and does not stutter on budget mobile hardware

Do not claim performance or SEO results that were not actually tested.