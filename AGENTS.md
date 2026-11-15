# software-factory — contract

Methodology for building software with agents. This vault is generic; it is not
tied to any repo. Read `Home.md` for the loop, then the skill for your stage.

## Read

- **`Home.md`** is the index and the loop. Read it before a milestone.
- **The skill for the stage you are in.** Each skill is one station.

## Write

- **Only write lines that change behavior.** A skill that an agent already obeys
  by default is a no-op. State the target behavior positively, not as a ban.
- **No project name, no stack, no source.** Any concrete technology or the
  example project is a placeholder to replace. This vault is shareable only if
  nothing in it is specific to one build.
- **Keep claims general, label inference.** "Agents can do this" is a claim; the
  conditions under which it holds are inference. Mark them so a later reader
  knows what to re-verify.
- **Update the vault when the method changes.** A skill that describes a loop a
  session no longer runs is worse than none: it will be trusted and acted on.
- **The loop guarantees outcomes, not stages.** It delivers failing tests that
  turn green, a real review, and learnings passed on. Match the machinery to the
  change: the full loop for large work, a failing test plus a review for a small
  tweak, oneshot for a one-off. Never skip the failing test or the review. A
  one-time change through the full loop is the costliest mistake.

## Traps

- **Grilling is not asking.** It is verifying. A claim without a confirmed
  source is an assumption; assumptions do not enter the spec.
- **Red tests that already pass are fake.** A test must fail before the code
  exists. If it passes without implementation, the test is the bug.
- **Review fixing is out of scope.** Review verifies and rejects; it does not
  implement. Fixes come back in green.
- **One context window per subticket.** Design subtickets small enough that a
  single agent reads the ticket and all assisting docs into one window and does
  the whole idea. Split larger work into subtickets first.
