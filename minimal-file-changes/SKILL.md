---
name: minimal-file-changes
description: Prefer small, local edits. Avoid creating new files or folders unless required by Laravel conventions or explicitly requested by the user.
---

# Minimal File Changes

## Goal

Deliver the requested outcome with the smallest reasonable set of changes:

- Minimise file churn
- Avoid new abstractions unless they are clearly necessary
- Preserve existing project structure and conventions

## Default Behaviour

- Prefer editing existing files over creating new ones.
- Prefer local refactors (within the touched file) over introducing new layers (services, helpers, traits, DTOs).
- Do not create new base directories or reorganise folder structure without explicit user approval.

## When to Create New Files

Only create new files when one of the following is true:

1) **Laravel conventions require it**
    - e.g. migrations, tests, policies, form requests, jobs, events/listeners, new models/components explicitly
      requested

2) **The user explicitly asked**
    - e.g. “create a new class”, “extract to a service”, “make a new component”

3) **A change would be unsafe or unmaintainable without separation**
    - If you believe separation is required, explain why in 1-2 sentences and ask for approval before creating the new
      file.

## One File at a Time Rule

If a new file is required:

- Create **only one** new file per iteration
- Then stop and ask if the user wants to proceed with the next file/change

## What NOT to Do

- Do not introduce new architectural patterns (Repository, Service layer, DTOs) by default.
- Do not create `Helpers/`, `Services/`, `Support/`, `DTO/`, or similar folders without explicit approval.
- Do not split code across multiple files “for cleanliness” unless asked.
- Do not do broad renames, mass formatting, or reorganisations unrelated to the request.

## How to Handle Tension Between “Best Practice” and “Minimal Change”

If the best-practice approach conflicts with minimal change:

- Provide the minimal-change solution first
- Optionally propose a follow-up improvement as a separate step
- Do not implement the broader refactor unless the user approves

## Anti-patterns

- “I extracted this into 5 new classes to improve readability” (without being asked)
- “I reorganised these folders to follow a cleaner architecture”
- “I created a base abstraction for future use”
