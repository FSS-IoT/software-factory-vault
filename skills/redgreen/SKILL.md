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

## Commit twice

Commit the check alone, then the code.

```
red:   reject a wrong password (fails)
green: reject a wrong password
```

The red commit is red in CI, and that is correct. It lives on the ticket branch
and never lands on main. That commit is the proof a reviewer can check out and
run.

## When review rejects the red

The check was fake: it passed, tested nothing, or tested the wrong thing. Rebuild
the pair. Do not patch on top of green, and do not rebase by hand.

1. Note the green commit: `git rev-parse HEAD`.
2. Back up the branch: `git branch backup/<ticket>`.
3. `git reset --hard <commit before red>`.
4. Write the corrected check. Run it. It must fail, because no code exists.
5. Commit it: `red: <behaviour> (fails)`.
6. Restore the implementation from the green commit, and only the implementation:
   `git checkout <green> -- <implementation paths>`.
   Do not restore test files. `git checkout <green> -- .` would put the fake check
   back.
7. Run the checks. They pass. Commit: `green: <behaviour>`.

If code and checks share a file, save `git diff <red> <green>` before the reset and
apply that patch instead.

Why not fix forward: a corrected check on top of green cannot fail, so it proves
nothing. Why not a new branch: the code is good, and review has already read it.
Why not rebase: the same rewrite, with more ways to lose work.

If the branch was pushed, the rebuild ends with `git push --force-with-lease` on
your own ticket branch.

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

Two commits: the failing check, then the code. The failing run is recorded, then
the passing run. Ready for review, not for shipping.
