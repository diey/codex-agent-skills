---
name: boost-search-docs-first
description: Use Laravel Boost search-docs to verify the correct, version-specific approach before implementing Laravel ecosystem features.
---

# Use Boost Docs First

## Goal

Avoid incorrect or outdated implementations by verifying the approach using Laravel Boost’s `search-docs` tool before
writing code.

This skill applies to Laravel ecosystem features where behaviour, APIs, or best practices vary by version.

## When to Apply

Use Boost `search-docs` **before coding** when the task involves any of the following:

- Laravel framework features (routing, middleware, validation, queues, auth)
- Livewire (including Volt and Livewire 3 behaviour)
- Flux UI (free or pro components)
- Fortify authentication features
- Tailwind CSS v4 utilities or patterns
- Pest v4 testing features
- Horizon, Pulse, Nightwatch, or other Laravel first-party packages

If you are unsure about syntax, behaviour, or best practice, assume this skill applies.

## How to Apply

1) Start with `search-docs` using **broad, simple queries**  
   Examples:
    - `['livewire pagination']`
    - `['fortify registration']`
    - `['tailwind v4 grid']`
    - `['pest browser test']`

2) Narrow the query only if needed after reviewing initial results.

3) Verify the approach against:
    - Installed package versions
    - Existing project patterns in sibling files

4) Only proceed to implementation once the documented approach is confirmed.

## What NOT to Do

- Do not rely on general Laravel knowledge if documentation is available.
- Do not guess APIs or options when Boost can confirm them.
- Do not copy patterns from older Laravel, Livewire, or Tailwind versions without verification.

## Exceptions

You may skip `search-docs` if:

- The change is trivial and already follows an existing, identical pattern in the codebase.
- The user explicitly instructs you to proceed without documentation lookup.

## Anti-patterns

- Writing code first and checking docs afterward.
- Mixing documentation from different major versions.
- Assuming behaviour based on pre-Laravel 11 conventions.
