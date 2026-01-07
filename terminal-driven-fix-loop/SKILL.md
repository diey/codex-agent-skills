---
name: terminal-driven-fix-loop
description: Use a terminal-first feedback loop where the user runs tools manually and provides output for fixes.
---

# Terminal-Driven Fix Loop

## Goal

Use a tight, terminal-first workflow:

- The assistant implements changes without running tools
- The user runs tests/formatters/static analysis manually
- Fixes are driven by terminal output

## Default Workflow

1) Implement the requested task without running tests, linters, formatters, or static analysis.
2) End with:
    - What changed (brief)
    - Suggested commands for the user to run (brief)
3) Wait for terminal feedback.

## When the User Pastes Errors

When the user provides terminal output:

- Use the command, file paths, line numbers, and messages from the output to guide fixes.
- Apply the smallest fix needed to address the reported error.
- Do not introduce unrelated refactors while fixing errors.
- Do not request code snippets unless the error output is ambiguous or lacks enough location/context to act.

## What to Ask For (When Needed)

Only request additional context if necessary, for example:

- The error output does not include a file path or line number
- The stack trace points to generated/vendor code without showing the caller
- The failure depends on runtime state that is not visible from output

If asking for more context, ask for the minimum needed.

## Tool Execution Policy

- Never run tests, linters, formatters, or other commands automatically.
- Do not assume permission to execute tools.
- You may suggest commands, but do not execute them.

## Anti-patterns

- Running tools without being asked
- Guessing causes instead of using terminal output
- Asking for snippets when output already identifies the location
- Fixing multiple unrelated issues in one pass
