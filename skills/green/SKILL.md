---
name: green
description: >
  Green stage: implement code to satisfy the red tests. Use after the red stage
  has failing tests, when it is time to write the implementation.
---

Green stage. Implement the red tests. The tests were written in the red stage;
now write the code that makes them pass.

## Method

1. Read the subticket and the assisting docs (spec, agents, existing code).
2. Read the failing red tests. They are the contract.
3. Write the minimal implementation that turns every red test green.
4. Run the tests. They pass. Nothing else changed.

## Rules

- **Minimal.** The implementation is the smallest thing that turns the red tests
  green. Do not add behavior the tests do not require.
- **Satisfy the tests, not the idea.** The idea is bounded by the red tests. If
  you feel tempted to add code the tests do not check, the scope is wrong.
- **One context window.** You have the ticket and assisting docs in one window.
  Do not open more than one session's worth of context. If you are looking for
  something you already read, you were over-scoped.
- **No skipping red.** A subticket is not done until its red tests are green.

## Completion criterion

Red tests green, run and passing. No new behavior beyond the tests. The failing
state from red stage is now satisfied.
