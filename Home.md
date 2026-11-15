# software-factory

A generalized, shareable methodology for building software with agents. Not
tied to any project. It is the process: brief, grilling, spec, tickets,
then the red / green / review loop per subticket.

## Read

- **`AGENTS.md`** first — the contract this vault holds.
- Then the skill for the stage you are in. Each skill is one stage of the loop.
- Templates in `templates/` if you are authoring a milestone or subticket.

## The loop

```
brief ──▶ grill ──▶ spec ──▶ tickets ──▶ [per subticket]
                          (planning)     red ──▶ green ──▶ review
```

- **Planning** (milestone setup): setup, brief, grilling, spec, tickets.
- **Execution** (per subticket, a new session each): red, green, review.

## Skills

| Stage | Skill | Owns |
|---|---|---|
| Setup | `skills/setup/` | Guide setup of the loop for a project: scope, issue storage, memory store. |
| Brief | `skills/brief/` | Write the milestone brief: facts before adjectives. |
| Grill | `skills/grill/` | Verify facts before spec: grilling session. |
| Spec | `skills/spec/` | Write spec, reviewed and signed before code. |
| Tickets | `skills/tickets/` | Split milestone into subtickets with blockers. |
| Red | `skills/red/` | Write failing tests that must turn green. |
| Green | `skills/green/` | Implement code to satisfy the red tests. |
| Review | `skills/review/` | Fresh session: verify, can reject, learn to pass on. |

## Templates

- `templates/milestone.md` — milestone + subticket scaffold.
- `templates/subticket.md` — one subticket, single idea, red/green.

## Invariants

- **One idea per subticket.** Minimal scope. Testable. Completable inside a
  single agent context window.
- **Tests define the contract.** Red tests fail first, turn green when the
  implementation is done.
- **Review is a fresh session.** No prior knowledge of how it was built. It
  verifies, it does not fix. It can reject and send work back.
- **Grilling before spec.** Facts confirmed before they are written down.
- **Pluggable.** No project name, no stack, no source. Replace the placeholders.
