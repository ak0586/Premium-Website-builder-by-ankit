---
trigger: always_on
---

# Code Quality Rules

## Purpose

Produce maintainable, production-quality code without unnecessary
complexity.

---

## 1. Understand Before Modifying

Before changing an existing project:

1. inspect the repository
2. inspect package.json
3. inspect the architecture
4. inspect existing components
5. inspect styling conventions
6. inspect design tokens
7. inspect dependencies
8. understand the existing implementation

Do not immediately rewrite the project.

---

## 2. Follow Existing Conventions

Prefer existing:

- naming conventions
- folder structure
- styling approach
- component patterns
- utility functions
- design tokens
- framework conventions

unless there is a strong reason to change them.

---

## 3. Avoid Overengineering

Do not introduce:

- unnecessary state management
- unnecessary backend services
- unnecessary databases
- unnecessary authentication
- unnecessary CMS
- unnecessary abstraction
- unnecessary dependencies
- unnecessary infrastructure

Simple websites should remain simple.

---

## 4. Components

Keep components:

- focused
- readable
- composable
- reusable where justified
- accessible

Avoid huge components containing unrelated responsibilities.

---

## 5. Type Safety

When the project uses TypeScript:

- maintain useful types
- avoid unnecessary `any`
- type component props
- keep data structures clear

Do not add types purely for verbosity.

---

## 6. State Management

Use the simplest appropriate state mechanism.

Do not introduce global state for local component state.

Do not install a state-management library unless the project actually
needs it.

---

## 7. Error Handling

Handle meaningful error states.

Do not silently ignore failures.

User-facing errors should be understandable.

---

## 8. Security

Never expose:

- API keys
- tokens
- passwords
- credentials
- private keys
- secrets

Never commit secrets to Git.

Never place secrets in:

- source code
- frontend code
- GEMINI.md
- CLAUDE.md
- `.agents`
- README files
- documentation

Use environment variables or secure secret storage.

---

## 9. Git

Before committing:

- inspect git status
- inspect the diff
- verify unintended files are not included
- verify no secrets are present
- verify the application still works

Use focused commits.

---

## 10. Production Build

Before completion, run the appropriate:

- lint
- type checking
- tests
- production build

where available.

Fix meaningful errors rather than ignoring them.

---

## 11. Browser Verification

When the project has a user-facing UI and browser inspection is
available:

1. start the application
2. inspect the rendered UI
3. test important interactions
4. inspect responsive behavior
5. fix issues
6. inspect again

Source code alone is not sufficient for visual QA.

---

## 12. Changes

Prefer focused changes.

Do not modify unrelated files.

Do not refactor working systems without a meaningful reason.

---

## 13. Documentation

Document important architectural decisions when they may not be
obvious to future developers.

Do not document trivial implementation details unnecessarily.

---

## 14. Dependencies

Keep dependencies intentional.

Before adding one, consider:

- functionality
- bundle impact
- maintenance
- security
- project fit

Remove unused dependencies when safe.

---

## 15. Final Code Review

Before completion ask:

- Is the code understandable?
- Is it unnecessarily complex?
- Are there duplicated patterns?
- Are there unused dependencies?
- Are errors handled?
- Are secrets protected?
- Does the production build pass?
- Does the actual website work?
- Does the implementation match the design system?

Prefer simple, reliable solutions.