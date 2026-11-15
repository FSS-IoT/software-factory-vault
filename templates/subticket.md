# <subticket-name>

**Subticket:** <M<digit>-<number>, e.g. M1-1>
**Status:** open
**Priority:** P0
**Depends on:** <which tickets must complete first>

## Idea

One sentence. The single thing this subticket does.

## Red

Write the failing test first. It must fail without the implementation.
- Test the idea from the subticket.
- Cover inputs, outputs, and the edge case that distinguishes correct from
  incomplete.
- Run: it fails. A passing test on a stub is a fake test.

## Green

Implement the minimal code that turns the red test green.
- Satisfy the red tests, not the idea beyond them.
- Nothing else changed.

## Review

Fresh session, no prior knowledge of how it was built. Verifies against the spec.
Tests are real, not fake. Change is committable/mergeable. Can reject with
comments. Does not fix.

## Blockers

- **Must complete first:** <tickets>
- **Unblocks:** <tickets>

## Assisting docs

Files a new session reads to do this subticket:
- Ticket: `<path to this ticket>`
- Spec: `<path>`
- Agents: `<path>`
- Existing code / tests: `<path>`

## Completion criterion

Red tests fail without implementation; green implements; review approves (or
rejects with comments). One idea, one context window.
