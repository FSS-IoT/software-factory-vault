---
name: Factory red green
description: >
  One subticket, one session: write the check, watch it fail, then the smallest
  code that makes it pass. Use after the tickets exist, for the next unblocked
  subticket.
---

# Red / green

Scope: **one subticket, one session**.

The check comes first. It is the contract, and the code is written to satisfy it.

Called `redgreen` in the files because opencode already has a Build agent, and two
things called build is one too many.

## Red

1. Read the subticket and its assisting docs: the spec criterion, the project
   page, the existing checks.
2. Write the check for the behaviour the subticket adds. Include the shape of the
   input and output, and the edge case that separates finished from nearly.
3. Run it. It **must fail**. Record the failure, the message or the assertion, in
   the subticket.
4. If it passes, the check is the bug. Fix the check before writing any code.

## Green

1. Write the smallest code that turns the check green.
2. Run it. Green.
3. Run the rest of the checks. Nothing else broke.
4. Stop. Do not add behaviour the check does not ask for.

## Rules

- **The check fails first.** A check written after the code proves the code runs,
  not that it does the right thing.
- **Minimal.** If you wrote more than the check needed, cut it back.
- **The check must not mirror the code.** If the check reads like the
  implementation, it is documenting it, not testing it.
- **One idea.** Anything you notice on the way goes in a new subticket, not in
  this one.
- **One session.** If you are re-reading things you already read, you were
  over-scoped. Stop and split.

## Completion criterion

The failing run is recorded, then the passing run, with nothing else changed.
Ready for review, not for shipping.
