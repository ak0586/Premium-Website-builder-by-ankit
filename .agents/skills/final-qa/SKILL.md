---
name: final-qa
description: Performs the final production-readiness review covering build, functionality, browser behavior, responsive design, accessibility, performance, SEO, security, factual content, visual quality, and Git readiness.
---

# Final QA Skill


## Purpose

Use this skill before declaring a website production-ready.

Final QA combines visual, functional, accessibility, performance, SEO, security, and code-quality checks.

## Build

Verify:

- production build succeeds
- no blocking errors
- no obvious warnings that affect production
- dependencies resolve correctly

## Browser

Verify:

- page loads
- navigation works
- buttons work
- forms behave correctly
- important links work
- external links are correct
- images load
- mobile navigation works
- AI concierge widget is present and functional:
  - opens and closes cleanly without trapping keyboard focus
  - chat mode sends and receives messages (or delivers clear placeholder demo responses)
  - voice push-to-talk requests microphone permission ONLY on user action
  - voice mode degrades gracefully with live transcript / text fallback if permission is denied or unsupported
  - fallback contact triggers (WhatsApp link, phone `tel:` link, contact form) work reliably

## Console

Check for:

- JavaScript errors
- failed network requests
- missing assets
- hydration errors
- repeated warnings

Fix meaningful issues.

## Responsive

Verify:

- mobile
- tablet
- desktop
- large desktop when relevant

Check:

- overflow
- typography
- spacing
- navigation
- buttons
- images
- forms
- sections

## Accessibility

Check:

- semantic HTML
- keyboard navigation
- visible focus
- labels
- alt text
- heading hierarchy
- sufficient contrast
- reduced motion
- touch targets

## SEO

Check:

- title
- meta description
- canonical URL when appropriate
- heading structure
- semantic content
- robots configuration
- sitemap when appropriate
- favicon
- Open Graph metadata when appropriate
- structured data when appropriate

For local businesses, consider appropriate local-business structured data without inventing information.

## Performance

Check:

- unnecessary dependencies
- oversized images
- unnecessary JavaScript
- excessive animation
- font loading
- layout shifts
- third-party scripts
- throttled mobile device check: verify 60fps and responsiveness under simulated mobile throttling (4x CPU slowdown, Fast 3G/Slow 4G)
- AI concierge widget loads asynchronously and does not regress Core Web Vitals (LCP < 2.5s, INP < 200ms, CLS < 0.1)
- 2D-first craft default verified; any 3D/WebGL moment passes gating criteria and does not stutter on budget mobile hardware

Prefer simple solutions.

## Content

Verify:

- no placeholder content remains
- no fake testimonials
- no invented reviews
- no invented awards
- no invented statistics
- no invented certifications
- no invented addresses
- no invented business history

If factual information is missing, keep a clearly marked placeholder or request the real information.

## Security

Verify:

- no API keys in frontend code
- no secrets in Git
- no credentials in documentation
- environment variables are used correctly
- `.env` files are ignored when appropriate

## Git

Verify:

- changes are intentional
- no generated junk is committed
- no secrets are committed
- repository state is understandable
- commit message is meaningful when committing

## Final Quality Gate

Do not declare production readiness if there is:

- broken functionality
- missing or non-functional AI concierge widget
- major responsive issue
- major accessibility issue
- exposed secret
- fake factual content
- obvious console error
- failed production build
- severe visual defect
- unoptimized 3D or animation stuttering on budget mobile hardware

Fix first.

## Final Question

Before completion, ask:

"Would I confidently show this website to a paying client?"

If the answer is no, continue refining.