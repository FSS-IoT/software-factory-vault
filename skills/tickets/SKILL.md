---
name: Factory tickets
description: >
  Split one milestone into subtickets, each a single idea with a check and its
  blockers, after the spec is signed. Use before handing work to a session.
---

# Tickets

Scope: **one milestone**.

A subticket is one idea, small enough for one session, with one check that proves
it. It is the unit of everything after this stage.

## Before you cut tickets

Read the milestone in the spec. Ask one question:

**Is the milestone detailed enough to cut tickets from?**

If not, stop. Grill the milestone first (`skills/grill/`), then come back. Cutting
tickets from a vague milestone is how three weeks disappear.

## Each subticket

- **Idea**: one sentence. Adding "and" means it is two subtickets.
- **Check**: what will fail before the code exists and pass after.
- **Blockers**: what must finish first. A subticket with no blockers can start now.
- **Assisting docs**: the files a new session must read. Name them, and create the
  missing ones first, so the next session is not guessing paths.

Start from `templates/subticket.md`.

## Where the tickets live

Read `PROJECT.md`. Where tickets live was decided when the project started. If
the page is missing, create it from `templates/project.md` before cutting
anything, so this is answered once and not per session.

| Storage | Milestone is | Subticket is | Blockers are |
|---|---|---|---|
| Local files | `milestones/<id>/milestone.md` | a file beside it | a line in the subticket |
| GitHub issues | a Milestone | an Issue, body from the template | "Blocked by #12", plus a task list |
| Other tracker | its equivalent | its equivalent | its equivalent |

Whichever you use, the milestone shows the same thing: what is done, what is
next, what is waiting.

## Rules

- **One idea per subticket.** If removing half leaves the check meaningful, the
  scope was too big.
- **No check, no subticket.** A ticket nobody can verify is a wish.
- **One context window.** The subticket, the spec, and the files it touches must
  fit in one session. Split bigger work first.
- **Planning only.** Write tickets, do not build them.
- **The ticket says why it exists.** One line pointing at the spec criterion.

## Completion criterion

Every criterion in the milestone has exactly one subticket. Each has an idea, a
check, stated blockers, and named assisting docs. The owner can read the list and
say what ships first.
