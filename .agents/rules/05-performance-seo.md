---
trigger: always_on
---

# Performance and SEO Rules

## Performance

## 1. Performance Is Part of Design

A premium website should feel fast.

Do not prioritize visual effects at the expense of responsiveness.

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

Do not claim performance or SEO results that were not actually tested.