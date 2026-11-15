---
name: tickets
description: >
  Split a milestone into subtickets: single idea, minimal scope, testable, with
  blockers. Use after the spec is signed, when you are ready to hand work to a
  session.
---

Split the milestone spec into subtickets. Each subticket is one idea, one
minimal, testable change, with clear blockers. Each completes inside a single
agent context window.

## Rules

- **One idea per subticket.** A subticket does one thing: add a failing test
  (red) and the code that turns it green. No two ideas in one subticket.
- **Minimal scope.** Cut until the change is one coherent unit. If removing half
  leaves the test still meaningful, the scope was too big.
- **Testable.** Every subticket ends with a green test. If you cannot write a
  test for it, the subticket is not ready.
- **Blockers stated per subticket.** Name which tickets may start now and which
  must wait on another ticket completing first. A subticket with no blockers is
  a candidate for the next session.
- **One context window.** Design the subticket small enough that one agent reads
  the ticket and all assisting docs (spec, agents, code) into one window and does
  the whole idea red then green. Split bigger work into subtickets first.
- **Follow the loop.** This is the planning stage. Do not implement. Tickets are
  written, not built.

## Output

For each subticket:
- **Idea** — one sentence of what it does.
- **Red test** — the failing test it must produce.
- **Green** — the implementation that turns it green.
- **Blockers** — tickets that must complete first, and tickets it unblocks.
- **Assisting docs** — the files a new session reads to do the work.

## Completion criterion

Every acceptance criterion in the spec has one subticket. Every subticket has an
idea, a red test, blockers stated, and assisting docs named. Each fits one
context window.
