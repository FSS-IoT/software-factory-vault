---
name: spec
description: >
  Write the spec from confirmed facts, reviewed and signed before code. Use when
  the grilling session is done and you are ready to define the work.
---

Write the spec. It is reviewed and signed before any code. The spec is the
contract every subticket and every test answers against.

## What the spec contains

- **Scope** — what the milestone delivers.
- **Acceptance criteria** — per deliverable, checkable, each tied to a subticket.
- **Non-goals** — what is out of scope.
- **Constraints** — the hard limits from the brief.

## Rules

- **Only confirmed facts enter.** Anything open from grilling is not in the
  spec; it is either resolved or a non-goal.
- **Every acceptance criterion is checkable.** If you cannot test it, it cannot
  be a criterion. Split fuzzy bounds into local, cheap checks.
- **One idea per subticket.** Each acceptance criterion maps to one subticket,
  which is one minimal, testable idea. Do not pack two ideas into one criterion.
- **State blockers per subticket.** Each subticket names which tickets can start
  now and which must wait on another ticket completing first.
- **Keep it project-agnostic.** Behavior, not the stack. The implementation stays
  a choice for tickets.

## The review gate

The spec is reviewed and signed before code. Do not write code until the spec is
signed. A spec that is not reviewed is trusted and built against silently.

## Completion criterion

Spec written with checkable acceptance criteria, each mapped to one subticket
with blockers stated. Spec reviewed and signed. No code written before signing.
