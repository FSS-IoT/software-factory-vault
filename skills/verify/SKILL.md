---
name: Factory review
description: >
  Verify a finished subticket in a fresh session: does it meet the spec, is the
  check real, is it shippable? Approve or reject. Does not fix. Use before a
  subticket is committed or shipped.
---

# Review

Scope: **one subticket**, after red/green, before ship.

You start with no memory of writing this. Recover everything from the files.

Called `verify` in the files because opencode's own `/review` command reviews a
diff in the current session, which is the opposite of what this stage needs.

## A fresh session means fresh

The requirement is isolation: the reviewer must not carry the author's
assumptions. That is a property of context, not of hardware, so it works the same
on a small local model. How to get it is recorded in `PREFERENCES.md`, because it
depends on the harness and the machine:

1. **A subagent**, if the harness has them and the machine can hold a second
   context. Fastest, and genuinely isolated.
2. **A new session**, after the author's session ends. Costs nothing, works
   anywhere, and is equally valid. Slower only because review runs after the
   build instead of beside it.
3. **A second harness or terminal.** Same isolation, more to manage.

Two sessions at once is an optimisation. If it does not fit the machine, use the
second rung and say so. Do not let the reviewer read the author's session, and do
not hand it a summary of what was done; give it the ticket, the spec, and the
paths.

## What you check

- **The spec**: each acceptance criterion for this subticket is met, or it is not.
  Not "looks good". Quote the criterion.
- **The check is real**: it failed before the code, it covers the behaviour the
  ticket adds, and it is not skipped, disabled, or passing on a stub.
- **Nothing else moved**: no half-built state, no other subticket's work, no
  leftover failing checks.
- **It is shippable**: coherent on its own, and the commit could stand.

If the project has CI, it owns the mechanical checks: does it build, do the
checks pass, did anything else break. This stage still owns the judgment, and no
pipeline can make it for you.

## Output

- **Approved**: what you verified, and the evidence you looked at.
- **Rejected**: what fails the spec, which check is fake, what is not shippable,
  and what the next red/green session must do. Specific enough to act on.

## Rules

- **Do not fix.** Not a typo, not a test. It goes back.
- **Do not trust the author's report.** Read the files.
- **Rejecting is a normal outcome**, not a failure of the stage.
- **Write down what was learned**: a constraint discovered, a mistake and its
  correction, something the next session would trip on. It goes in the project's
  docs, or in `PREFERENCES.md` if it is about how the owner wants work done.
- **The owner sees the verdict.** One screen: approved or rejected, and the
  evidence.

## Completion criterion

Approved with evidence, or rejected with specific, actionable comments. No
approval without proof the check fails without the code.
