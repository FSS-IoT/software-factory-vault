# software-factory, the contract

How work gets done here. Read `Home.md` for the shape, then the stage file you are
in.

## Read order

1. `Home.md` for the levels and the stages.
2. `PREFERENCES.md` for how this owner wants it done. It wins over a stage file
   when they disagree.
3. The stage file for the work in front of you.

**Setup is an installer, not a stage.** It runs once per machine and is never
part of the loop. The loop starts when the owner says what they want to build.

## Write

- **Only write what changes behaviour.** A line an agent already obeys is noise.
- **Preferences go in `PREFERENCES.md`**, in the owner's words, with a date. The
  same correction three times becomes a proposal to change the stage file.
- **A change to the method goes in the stage file**, with a line in `CHANGES.md`.
- **No project, stack, or machine specifics.** Those belong on the project's page
  and in its `BRIEF.md`. This vault stays shareable.
- **The copy is the seed.** Once installed, the owner's copy is the source of
  truth. This repository is only the starting point.

## Traps

- **Grilling is not asking permission.** It is finding out what is true, before
  code makes being wrong expensive.
- **A check that already passes is fake.** If it passes on a stub, the check is
  the bug.
- **Review does not fix.** It verifies and rejects. Fixes go back through red and
  green.
- **A bare milestone is not ready for tickets.** If it has no subtickets and the
  spec does not cover it, grill it first.
- **One context window per subticket.** If the session is re-reading to remember,
  the subticket was too big. Split it.
- **Review must be a fresh session**, not the author with a clear head. On
  opencode, a subagent.
