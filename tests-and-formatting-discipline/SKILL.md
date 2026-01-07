---
name: tests-and-formatting-discipline
description: Maintain testing and formatting discipline aligned with the repository CI pipeline without automatically running tools.
---

# Tests & Formatting Discipline

## Goal

Maintain code quality and CI stability by:

- Designing changes to be testable
- Updating or adding tests when behaviour changes
- Writing code that conforms to formatting standards
- Never running tests, linters, or formatters without explicit user approval

## Project Commands (Reference Only)

Use these exact command names when suggesting verification steps:

- `composer test` — Clears cached config and executes the full Pest test suite.
- `composer clean` — Runs Laravel Pint and Prettier.
- `composer analyse` — Runs Larastan static analysis.

Do not claim these were run unless the user confirms and provides results.

## Testing Expectations

- Behaviour changes must be covered by tests.
- Prefer feature tests unless logic is truly isolated.
- Use existing factories, states, and helpers.
- Follow existing test structure and naming conventions.

If behaviour changes and no test is added:

- Explicitly state why
- Offer test coverage as the next step

## Formatting Expectations

- Write code that already conforms to Pint and Prettier standards.
- Avoid unrelated or drive-by formatting changes.
- Do not reformat files outside the scope of the change.

Note:

- On PRs targeting `development`, the lint workflow may run `composer clean` and auto-commit formatting fixes.

## Tool Execution Policy

- Never run `composer test`, `composer clean`, `composer analyse`, or any tooling automatically.
- You may suggest commands, but execution is always the user’s responsibility.

## End-of-Task Output

After completing an implementation, provide:

1) A brief list of files changed
2) A minimal list of suggested commands the user can run to validate the change

## Anti-patterns

- Running tools without permission
- Claiming tests, lint, or analysis passed without evidence
- Changing behaviour without mentioning test coverage
- Introducing unrelated formatting diffs
