# software-factory

How to take an idea to something running, with agents, in stages.

Generic on purpose: no project, no stack, no operating system, no harness.

**This vault is a seed.** Once it is copied into someone's own store, that copy is
the source of truth. Edit it. It is meant to learn how its owner works, which is
what `PREFERENCES.md` is for.

## Start here

| You are | Read |
|---|---|
| A person, first time | `START-HERE.md` |
| An agent, first session | this file, then the stage you are in |
| Adding a project | `skills/setup/SKILL.md` |
| Wondering why it looks like this | `CHANGES.md` |
| Stuck on a word | `GLOSSARY.md` |

An agent should be told, once, where this vault lives. One line in whichever
file the harness reads at session start:

> The software factory method lives at `<path to this vault>/Home.md`. Read it
> before planning or starting work.

That is the whole install. Nothing needs to be copied into a skills folder.

## The shape

Two levels. The project is described once; each milestone runs the loop.

```
project    brief ─▶ grill ─▶ spec        one, and it may cover several milestones
                               │
milestone           ┌──────────┴───────────┐
                    │                      │
             not detailed enough        detailed
                    │                      │
                 grill ──────▶ tickets ◀───┘
                                  │
                          per subticket:
                  red, then green ─▶ review ─▶ ship
```

**Grilling is a move, not a stage.** It happens at project start, on a milestone
that has no subtickets yet, or on any topic that needs pinning down. It is where
facts get found, and it is the cheapest place to be wrong.

## Stages

| Stage | Scope | File | Produces |
|---|---|---|---|
| Setup | once | `skills/setup/` | a pointer in the harness, issue storage, a deploy path, the first project |
| Brief | project | `skills/brief/` | the free-form dump, written down as facts, constraints, non-goals |
| Grill | any time | `skills/grill/` | confirmed facts and decisions, with sources |
| Spec | project | `skills/spec/` | the contract, signed, criteria mapped to milestones |
| Tickets | milestone | `skills/tickets/` | one subticket per criterion, with blockers |
| Red / green | subticket | `skills/redgreen/` | a check that failed, then code that makes it pass |
| Review | subticket | `skills/verify/` | approved or rejected, with evidence |
| Ship | subticket | `skills/ship/` | committed, pushed, live, verified |

The class that teaches this calls a stage a **station**. Same thing.

Two files are named differently from the words used here, on purpose: `redgreen`
because opencode already has a Build agent, and `verify` because opencode's
`/review` command reviews a diff in the current session, which is the opposite of
the fresh session this stage needs.

## Match the machinery to the change

The loop exists to guarantee three things: a check that failed before it passed,
a review by a session that did not write the code, and what was learned written
down. Do the smallest slice that still delivers all three.

- **Large project, or work with many dependencies** runs the whole thing.
- **A small, local change** skips brief, grill, spec and tickets. One failing
  check, the fix, one review.
- **A one-off** skips milestones and subtickets entirely. Write it, check it,
  review it once.

Never skip the failing check or the review. Those are outcomes, not stages. A
one-time tweak dragged through the full loop is the most expensive mistake the
method can make.

## Templates

- `templates/brief.md` and `templates/spec.md` for the two project documents.
- `templates/milestone.md` and `templates/subticket.md` for the work.
- `templates/project.md` for the per-project page: where the repo is, where it
  deploys, what this project does differently.

## Invariants

- **One idea per subticket.** It fits one session, one context window, one check.
- **The check fails first.** A check that passes without the code is the bug.
- **Review is a fresh session, and it does not fix.** It rejects and sends back.
- **Facts before the spec, the spec is signed before code.**
- **The copy is the owner's.** Preferences go in `PREFERENCES.md`; a change to the
  method itself goes in the stage file, with a line in `CHANGES.md`.
