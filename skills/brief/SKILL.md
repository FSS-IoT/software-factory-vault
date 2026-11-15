---
name: brief
description: >
  Write a milestone brief: facts before adjectives. Use when starting a
  milestone, defining scope, or asking an agent to set up a milestone.
---

Write the milestone brief. Facts before adjectives.

## Output

A brief with three sections:
- **Facts** — what must be true, each with a source or a grilling task.
- **Constraints** — hard limits (local-only, no paid APIs, no auth, uncensored).
- **Non-goals** — what this milestone does not do.

## Rules

- **Facts before adjectives.** A feature description without a confirmed fact is
  an adjective, not a requirement. Adjectives go in non-goals or become grilling
  tasks.
- **Every fact is checkable.** If you cannot verify it, it is not a fact: it is
  a grilling task for the next stage.
- **Non-goals are load-bearing.** A milestone that does not state what it does
  not do will do more. List them.
- **No stack, no project.** The brief names behavior, not the tool that builds
  it. Leave the implementation choice for tickets.

## Completion criterion

Brief written with facts checked, constraints and non-goals stated. Grilling
tasks listed for any unconfirmed fact.
