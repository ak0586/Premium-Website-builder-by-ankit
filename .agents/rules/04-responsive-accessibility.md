---
trigger: always_on
---

# Responsive and Accessibility Rules

## Purpose

Every website must provide a high-quality experience across screen
sizes and abilities.

---

# Responsive Design

## 1. Design for Each Breakpoint

Consider:

- mobile
- tablet
- laptop
- desktop
- large desktop

Do not simply shrink desktop layouts.

---

## 2. Mobile Is a First-Class Experience

Check mobile intentionally.

Pay particular attention to:

- navigation
- hero composition
- typography
- spacing
- image cropping
- buttons
- forms
- grids
- cards
- content order
- touch targets
- overflow

---

## 3. Typography

Prevent:

- awkward line breaks
- excessive heading sizes
- unreadably small body text
- uncontrolled text overflow

Responsive typography should preserve hierarchy.

---

## 4. Layout

Avoid:

- horizontal overflow
- fixed widths that break mobile
- content trapped outside the viewport
- desktop-only interactions

Use responsive layouts intentionally.

---

## 5. Touch Targets

Interactive elements should be comfortably usable on touch devices.

Avoid tiny controls or tightly packed actions.

---

# Accessibility

## 6. Semantic HTML

Prefer semantic HTML:

- header
- nav
- main
- section
- article
- footer
- button
- form
- label

Do not use divs where semantic elements are more appropriate.

---

## 7. Keyboard Navigation

Interactive components should work with keyboard navigation.

Check:

- Tab
- Shift+Tab
- Enter
- Space
- Escape
- arrow keys where appropriate

---

## 8. Focus States

Interactive elements must have visible focus states.

Do not remove browser focus indicators without replacing them with an
accessible alternative.

---

## 9. Forms

Every important form control should have an accessible label.

Errors should be understandable.

Focus should be handled appropriately after validation when relevant.

---

## 10. Images

Use meaningful alt text when an image conveys information.

Use empty alt text for genuinely decorative images when appropriate.

Do not stuff keywords into alt attributes.

---

## 11. Contrast

Maintain sufficient contrast between:

- text
- background
- controls
- borders
- interactive states

Do not sacrifice readability for subtle aesthetics.

---

## 12. Motion Accessibility

Respect:

`prefers-reduced-motion`

Reduced-motion users must still receive a complete usable experience.

---

## 13. Screen Readers

Important information must not depend solely on:

- color
- animation
- hover
- visual position

Provide semantic alternatives where needed.

---

## 14. Responsive QA

Before completion inspect at least:

- narrow mobile
- normal mobile
- tablet
- desktop
- large desktop

When browser inspection is available, inspect the actual rendered
result.

---

## 15. Final Test

Ask:

- Can a keyboard user navigate?
- Are focus states visible?
- Are labels present?
- Is text readable?
- Is contrast adequate?
- Does mobile work?
- Is there horizontal overflow?
- Does reduced motion work?
- Are important states understandable without animation?