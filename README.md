# Codex Skills

This directory contains **repository-level Codex skills** that define how Codex should behave when working on this
project.

These skills act as **guardrails**, not hard rules. They encode the project’s real development workflow, GitHub Actions
enforcement, and quality expectations so they do not need to be restated on every request.

Codex automatically discovers and applies these skills when operating inside this repository.

Most of it is for personal use in **Laravel** project.

---

## Included Skills

### ask-clarifying-questions

Ensures Codex asks the **minimum necessary clarifying questions** before implementation when a request is ambiguous or
underspecified.

**Purpose**

- Prevent wrong assumptions
- Reduce rework
- Avoid premature implementation

---

### boost-search-docs-first

Requires Codex to use **Laravel Boost `search-docs`** to verify version-specific behaviour before implementing Laravel
ecosystem features.

**Purpose**

- Prevent outdated Laravel, Livewire, Tailwind, Pest, or Flux UI patterns
- Ensure solutions match installed package versions

---

### minimal-file-changes

Encourages **small, local edits** and discourages unnecessary file creation or architectural changes unless explicitly
requested or required by Laravel conventions.

**Purpose**

- Prevent file and folder explosion
- Avoid over-architecture
- Preserve existing project structure

---

### tests-and-formatting-discipline

Defines testing and formatting **expectations** without allowing Codex to run tools automatically.

**Purpose**

- Keep behaviour changes testable
- Align with CI expectations (`composer test`, `composer clean`, `composer analyse`)
- Maintain code quality without breaking the terminal-driven workflow

---

### terminal-driven-fix-loop

Defines a **terminal-first feedback loop** where the user runs tests, linters, and formatters manually, and Codex fixes
issues based on pasted terminal output.

**Purpose**

- Keep execution under user control
- Enable fast, deterministic fix cycles
- Avoid Codex running tools without permission

---

### pull-request-format

Validates pull request **source → target branch rules** and generates standardised PR titles and descriptions that match
GitHub Actions enforcement.

**Purpose**

- Enforce branch policy before PR creation
- Deny invalid PR requests early
- Generate consistent PR titles and descriptions
- Reflect CI, lint, and frontend build automation accurately

---

## Notes

- These skills are **automatically loaded** by Codex when working in this repository.
- They do **not override** system rules, Laravel Boost rules, or GitHub Actions.
- Codex may refuse to proceed when a request violates enforced branch or workflow rules.
- New skills should only be added when **recurring friction** is observed.

Keep this directory small, intentional, and focused on real workflow constraints.
