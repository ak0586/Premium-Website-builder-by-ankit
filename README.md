# Premium Website Builder

Master design system, agent rules, reusable workflows, and engineering standards for creating bespoke, production-grade websites for businesses and clients.

## Overview

The **Premium Website Builder** repository serves as the central design system and operational foundation for building premium client websites.

It defines the architectural, visual, accessibility, performance, research, and quality standards required to create websites that feel:

- **Professionally Art-Directed**: Bespoke visual identities tailored to each business, audience, market, and brand.
- **Commercially Purposeful**: Engineered around clear conversion paths, trust signals, business goals, and user needs.
- **Accessible & Performant**: Semantic HTML, responsive layouts, accessible interactions, optimized assets, and strong performance.
- **Production-Ready**: Visually inspected, technically verified, responsive, accessible, secure, and free from generic AI design patterns.
- **Distinctive by Client**: Shared engineering quality and design discipline without forcing every client website into the same visual style, including a category-specific motion concept for each client's industry rather than a generic animation layer.

---

## Repository Structure

```text
Premium-Website-builder-by-ankit/
│
├── .agents/
│   ├── rules/
│   │   ├── 01-premium-design.md
│   │   ├── 02-ui-system.md
│   │   ├── 03-animation.md
│   │   ├── 04-responsive-accessibility.md
│   │   ├── 05-performance-seo.md
│   │   └── 06-code-quality.md
│   │
│   └── skills/
│       ├── new-client/
│       │   └── SKILL.md
│       ├── premium-ui/
│       │   └── SKILL.md
│       ├── prospecting/
│       │   └── SKILL.md
│       ├── visual-qa/
│       │   └── SKILL.md
│       └── final-qa/
│           └── SKILL.md
│
├── design-system/
│   ├── category-motion.md
│   ├── color.md
│   ├── components.md
│   ├── layout.md
│   ├── motion.md
│   ├── principles.md
│   ├── spacing.md
│   └── typography.md
│
├── docs/
│   ├── client-design-brief-template.md
│   ├── premium-stack.md
│   └── references.md
│
├── CLAUDE.md
├── GEMINI.md
├── README.md
└── .gitignore
```

## Category-Specific Motion

`design-system/category-motion.md` is the canonical reference for
deriving an industry-aware motion concept for each client, using a
six-question derivation method plus an illustrative motion bank across
common client industries (dental, medical, salon, automotive,
electronics repair, food/hospitality, real estate, fitness, legal,
finance, technology, education, travel, and creative/portfolio work).

It is referenced from `.agents/rules/03-animation.md`,
`design-system/motion.md`, `docs/client-design-brief-template.md`, and
`.agents/skills/new-client/SKILL.md` rather than duplicated in each of
those files. The industry motion bank is inspiration, never a
template — two clients in the same industry must receive different
executions.
