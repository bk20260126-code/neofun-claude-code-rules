---
name: karpathy-guidelines
description: Behavioral guidelines to reduce common LLM coding mistakes. Use when writing, reviewing, or refactoring code to avoid overcomplication, make surgical changes, surface assumptions, resolve instruction conflicts, and define verifiable success criteria.
---

# Karpathy Guidelines

Apply these rules to non-trivial coding work. Prefer project-specific instructions when they are more specific. Do not silently blend conflicting rules. State the selected rule and the reason.

## Execute in this order

1. State the request boundary, assumptions, and success checks.
2. Read the relevant code, immediate callers, tests, and local conventions before editing.
3. Choose the smallest change that meets the success checks.
4. Make only request-traceable changes. Remove only unused code created by the change.
5. Run the relevant verification. Report what passed, what was not run, and what remains uncertain.

For trivial, obvious changes, keep the same safeguards but use proportional effort.

## Apply the four foundations

### Think Before Coding

- Surface assumptions and ambiguity before implementation.
- Present alternatives instead of choosing one silently.
- Name a simpler approach when one exists.
- Stop and ask when missing information changes the work.

### Simplicity First

- Build the smallest solution that meets the request.
- Avoid speculative features, configuration, abstractions, and impossible-case handling.
- Rewrite an overgrown solution into the smallest clear version.

### Surgical Changes

- Limit the diff to lines needed for the request.
- Preserve unrelated code, comments, formatting, and conventions.
- Mention unrelated debt without deleting or refactoring it.
- Remove imports, variables, and functions made unused by the current change only.

### Goal-Driven Execution

- Translate work into observable success criteria.
- For bug fixes, reproduce the bug before fixing it when practical.
- For refactors, verify behavior before and after.
- For multi-step work, state each step with its verification check.

## Apply the eight operating rules

- Use model judgment for ambiguity, classification, and drafting. Use deterministic tools for routing, retries, transformations, and facts they can establish.
- Respect the task and session budget. Summarize or stop before a budget breach becomes hidden drift.
- Resolve conflicts by evidence, recency, or local convention. Do not average incompatible instructions.
- Read exports, callers, utilities, and tests before changing an unfamiliar area.
- Write tests that protect the business intent, not only the current implementation.
- Checkpoint after significant steps so the current state, verification, and remaining work are explicit.
- Match the codebase's conventions. Surface harmful conventions instead of quietly creating a second style.
- Fail loudly. Never report completion or passing tests when relevant work or verification was skipped.

## Completion format

Report the result first. Then list changed files, verification evidence, skipped checks, unresolved assumptions, and the smallest next action if work remains.
