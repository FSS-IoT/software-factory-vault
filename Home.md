# software-factory

How to take an idea to something running, with agents, in stages.

Generic on purpose: no project, no stack, no operating system, no particular
harness.

**This vault is a seed.** Once it is copied into someone's own store, that copy is
the source of truth. Edit it. It is meant to learn how its owner works, which is
what `PREFERENCES.md` is for.

It can stand alone, or live as one subvault of a general vault that also holds
their projects and notes. `templates/general-vault/` is the skeleton for the
second case.

## Start here

| You are | Read |
|---|---|
| A person, first time | `START-HERE.md` |
| An agent, first session | this file, then the stage you are in |
| Installing it on a machine | `skills/setup/SKILL.md` |
| Wondering why it looks like this | `CHANGES.md` |
| Stuck on a word | `GLOSSARY.md` |

An agent should be told, once, where this vault lives. One line in whichever
file the harness reads at session start:

> The software factory method lives at `<path to this vault>/Home.md`. Read it
> before planning or starting work.

That is the whole install. Nothing needs to be copied into a skills folder.

## How it starts

Nobody has to name a file. An agent that has read this page maps what the person
says to the right one:

| They say | Open |
|---|---|
| "set up the software factory", "install this", "I cloned this repo" | `skills/setup/` |
| "set up a vault", "where should my notes live" | `skills/vault-setup/` |
| "I want to build ...", "new project" | `skills/brief/` |
| "research this", "I need to know whether ..." | `skills/research/` |
| "grill me on ...", "I am not sure what I want" | `skills/grill/` |
| "write the spec", "what are we agreeing to" | `skills/spec/` |
| "break it down", "what is next", "cut tickets" | `skills/tickets/` |
| "build this one", "make the check fail first" | `skills/redgreen/` |
| "review this", "is it right", "check my work" | `skills/verify/` |
| "ship it", "deploy", "is it live" | `skills/ship/` |

Setup is an installer, not a station. It runs once per person, and it is the only
thing that has to be asked for by name. `skills/vault-setup/` is the second installer:
it builds the general vault the factory can live in.

## The shape

Two levels. The plan is made once; the loop runs on every milestone.

```
project    brief ─▶ research? ─▶ grill ─▶ spec       once per project
                                            │
                                            ▼
milestone  tickets ─▶ red, then green ─▶ review     a ticket closes here
   ▲                                        │
   │                                        ▼
   └──── next milestone ◀──── ship ─────────┘        ship closes the milestone
```

**Grilling is a move, not a stage.** It happens at project start, on a milestone
that has no subtickets yet, or on any topic that needs pinning down. It is where
facts get found, and it is the cheapest place to be wrong.

**Shipping is the milestone's last move.** A milestone is done when its objectives
are complete and the thing is live. Some projects ship on every ticket instead;
that is a preference, set in `PREFERENCES.md`, not a rule of the method.

## Stages

**Starters**, once per project. They produce the plan, and they are not stations:

| Starter | File | Produces |
|---|---|---|
| Brief | `skills/brief/` | the sentence that starts it, and a file if the idea is big |
| Research (optional) | `skills/research/` | the facts the idea needs, written into the vault |
| Grill | `skills/grill/` | confirmed facts and decisions, with sources |
| Spec | `skills/spec/` | the signed contract, criteria mapped to milestones |

**The loop**, once per milestone:

| Station | Scope | File | Produces |
|---|---|---|---|
| Tickets | milestone | `skills/tickets/` | one subticket per criterion, with blockers |
| Red / green | subticket | `skills/redgreen/` | a check that failed, then code that makes it pass |
| Review | subticket | `skills/verify/` | the ticket closed, with evidence |
| Ship | milestone | `skills/ship/` | merged, deployed, verified, milestone closed |

The class that teaches this calls the four loop steps **stations**. Same thing.

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
- `templates/project.md` for a standalone project page: where the repo is, where
  it deploys, what this project does differently.
- `templates/general-vault/` is the skeleton for a person's whole vault, which
  `skills/vault-setup/` copies. When they have a vault, the project page lives in
  `projects/<name>.md` instead of in the repo.

## Invariants

- **One idea per subticket.** It fits one session, one context window, one check.
- **The check fails first.** A check that passes without the code is the bug.
- **Review is a fresh session, and it does not fix.** It rejects and sends back.
- **Facts before the spec, the spec is signed before code.**
- **The copy is the owner's.** Preferences go in `PREFERENCES.md`; a change to the
  method itself goes in the stage file, with a line in `CHANGES.md`.
