---
name: Factory review
description: >
  Verify a finished subticket in a fresh session: does it meet the spec, is the
  check real, is it shippable? Approve or reject, then close the ticket. Does
  not fix. Use before a subticket is closed.
---

# Review

Scope: **one subticket**, after red/green. Approval closes the ticket; shipping
is a milestone move, not a ticket one.

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
- **The check is real**: open the red commit, run the check, and watch it fail.
  A check that passes there was never a check. It also has to cover the behaviour
  the ticket adds, and it must not be skipped, disabled, or passing on a stub.
- **Nothing else moved**: no half-built state, no other subticket's work, no
  leftover failing checks.
- **It is shippable**: coherent on its own, and the commit could stand.

If the project has CI, it owns the mechanical checks: does it build, do the
checks pass, did anything else break. This stage still owns the judgment, and no
pipeline can make it for you.

## Break it on purpose

Reading is not enough. Some broken code looks right.

Change the code in a way a person would not notice, run the checks, and see if the
checks notice:

- Delete a term from a formula.
- Invert a condition, or change `>` to `>=`.
- Change a bound by one.
- Remove a clamp, a reset, or a normalisation step.
- Change a default value.
- Skip one branch of a loop.

Apply one mutation, run the whole suite, then revert it. A mutation is temporary:
never commit it, never leave it in the tree, and never test it on main.

If every check still passes, one of two things is true:

1. **The mutation is equivalent.** It does not change behaviour, so the survivor is
   harmless. Say so and move on.
2. **The behaviour is not checked.** The checks around it are decoration, and the
   ticket goes back.

Decide by running the thing, not by reading the tests. If the output changes for a
real input and no check notices, it is case 2.

This pays most where checks go vague: numbers, timing, randomness, "looks about
right" output, and checks that only assert nothing crashed.

Record the mutation and the result in the ticket. One or two mutations is enough;
this is a probe, not a mutation-testing campaign. If the project already has a
mutation tool, use it. Most do not, and editing by hand takes a minute.

A real one: deleting the copy term from a jitter function changed nothing a check
could see. Twelve checks stayed green. The behaviour was never tested, and the
"fix" under review had quietly removed a check.

## Output

- **Approved**: what you verified, and the evidence you looked at. Approval
  closes the ticket; put the commit id on it.
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
approval without proof the check fails without the code. For numeric, random or
timing behaviour, one mutation the suite caught is part of that proof.
