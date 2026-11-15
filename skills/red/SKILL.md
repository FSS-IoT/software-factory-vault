---
name: red
description: >
  Red stage: write failing tests that must turn green when the implementation is
  done. Use when starting a subticket, before any implementation code exists.
---

Red stage. Write the tests first. They define the contract. The code is written
to satisfy these tests.

## Method

1. Read the subticket. Its idea is the only thing to test.
2. Read the assisting docs (spec acceptance criteria, agents, existing tests).
3. Write tests that fail without the implementation:
   - The behavior the subticket adds.
   - The shape of inputs and outputs.
   - The edge case that distinguishes correct from incomplete.
4. Run them. They **must fail** — a red test that already passes is a fake test,
   and the fake test is the bug.

## Rules

- **Tests define the contract, not guess it.** Derive them from the spec, not from
  "what feels right."
- **Fail first.** Never write a test that passes without the code. If it passes
  on an empty stub, the test does not test the behavior.
- **No implementation leaks into the test.** The test must not hard-code the one
  way the code happens to do it. If the test and code read the same, the test is
  documenting the code.
- **One idea, one subticket.** Test only what this subticket adds.

## Completion criterion

Tests written and run, failing without the implementation. The failing state is
recorded (error, message, or assertion) before green stage begins.
