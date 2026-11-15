---
name: review
description: >
  Review stage: a fresh session with no prior knowledge of how the work was
  built. Verifies code against the spec, proves the tests are real, and can
  reject with comments. Does not fix. Use at the end of a subticket before the
  change is committed or merged.
---

Review stage. Start with no knowledge of how the work was built. Your job is to
verify, not to fix. You can send the change back with comments.

## What you verify

- **Code complies to the spec.** Each acceptance criterion is met. Not "looks
  good" — each checkable criterion in the spec is satisfied or not.
- **Tests are real, not fake.**
  - They fail without the implementation. If a test passes on a stub, it is fake.
  - They cover the behavior the subticket adds, not just re-read the code.
  - The green run is genuine, not a skipped or disabled test.
- **The change is committable or mergeable.** It is coherent, no half-built
  state, no left-behind failing tests from an earlier stage.

## Rules

- **You are a fresh session.** Do not trust the previous session's claims. Read
  the subticket, the spec, and the code yourself. Recover the context from the
  files, not from memory.
- **No fixing.** Review verifies and rejects. If something is wrong, leave it for
  green to fix. Do not implement in this stage.
- **You can reject.** If the code or the tests do not hold, reject with specific
  comments: what fails the spec, which test is fake, what is not committable.
  Rejection is a valid outcome, not a failure of the stage.
- **Learn to pass on.** Update the vault and docs with what a future session
  should know: a mistake made, its correction, a constraint discovered. A
  session that ends without writing a line teaches the wrong lesson.
- **Update documentation and vaults.** Corrections go in the owning vault. This
  is where the learning lives.

## Output

- **Approved** — code complies, tests real, change committable. Ready to commit
  or merge.
- **Rejected** — specific comments on what fails the spec, which test is fake,
  what is not committable, and what green must do.

## Completion criterion

Either approved (spec satisfied, tests proven real, change committable) or
rejected with specific, actionable comments. No approval without proof the tests
fail without the implementation.
