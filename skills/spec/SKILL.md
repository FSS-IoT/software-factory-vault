---
name: Factory spec
description: >
  Write the project spec from confirmed facts, get it signed by the owner, and
  keep it current as milestones land. Use when the grill is done, before any
  code is written.
---

# Spec

Scope: **project**. One spec, and it usually covers more than one milestone.

The spec is the contract. Tickets answer to it, and every check answers to a
criterion in it.

## What it contains

- **Scope**: what the project delivers.
- **Milestones**: the order things become real, one line each. Mark the ones
  that are not detailed yet. Those get grilled before they get tickets.
- **Acceptance criteria**: per milestone, checkable, each one small enough to
  become a single subticket.
- **Non-goals**: what this project will not do.
- **Constraints**: the hard limits carried over from the brief.

Start from `templates/spec.md`. The spec lives in the project root, beside the
code, and it is versioned like everything else.

## Decisions that outlive the spec

A choice with a reason that will be argued again gets one short page in
`docs/adr/` in the repo, numbered and dated: what was chosen, what was rejected,
and why. The spec points at it. That page is what ends the argument in six
months.

## The signing gate

The owner signs. Not the agent, not a reviewer agent.

1. Show one screen: what it delivers, what it does not, the criteria, and any
   open question.
2. Wait. Answer what they ask. Change what they change.
3. When they say yes, write it at the bottom of the spec:

```
Signed: <name>, <date>
```

No code before that line exists. A spec nobody signed is trust, not agreement.

## Rules

- **Only confirmed facts.** Anything open from the grill is either resolved, or a
  non-goal.
- **Every criterion is checkable.** If it cannot become a check, it is not a
  criterion yet.
- **One idea per criterion**, so one criterion maps to one subticket.
- **No stack.** Behavior, not the tool. The choice belongs in the project page.
- **The spec changes when the project changes**, and the change is dated. A
  signed spec that quietly drifts is worse than no spec.

## Completion criterion

Spec written, criteria checkable, milestones ordered, non-goals stated, owner
signed. No code written before the signature.
