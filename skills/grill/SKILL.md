---
name: Factory grill
description: >
  Interview the owner to find the facts: at project start, on a milestone that
  has no subtickets yet, or on a single topic that needs pinning down. Use
  before writing or changing a spec, and whenever something is vague or
  assumed.
---

# Grill

Grilling is how facts get found. It is an interview, not a review of what the
owner already wrote.

Three scopes, same skill:

| Scope | When | Produces |
|---|---|---|
| Project | Once, after the brief, before the spec | The facts and decisions the spec is built on |
| Milestone | A milestone with no subtickets that needs more detail | Enough decisions to cut tickets |
| Topic | Any time the owner says "hash this out" | One decision, recorded |

## Interview mode

This is the project scope, and the milestone scope when the milestone is bare.

Ask the questions the owner has not thought of. Batch them, most important
first, and keep going until a question would no longer change the build.

Starters that work on almost anything:

- What happens when it fails? Who finds out, and how?
- Who else uses this, and what do they expect?
- What must never happen, even if something else breaks?
- What is the smallest version that is still useful?
- What already exists that this replaces or has to live beside?
- What would make you abandon this in a month?
- What did you decide before you started talking to me?

Do not interview for an hour if twenty minutes settles it. Stop when the answers
stop changing.

## Audit mode

For any claim already written, and for a topic scope:

- **How do you know?** A source, a measurement, or a decision the owner makes now.
- **What breaks if it is wrong?** Say the consequence, so the cost is felt.
- **Can it be checked now?** If not, it is open, not a fact.

## Output

- **Confirmed facts**, each with its source.
- **Decisions**, in the owner's words, with the date.
- **Open items**, each with a resolution: check it, drop it, or make it a
  non-goal.

At project scope the output feeds the spec. At milestone scope it feeds the
tickets. At topic scope it goes in the project's docs, near the code it affects.

## Rules

- **Record as you go.** A decision that lives only in the chat is lost.
- **Label inference.** If you worked something out rather than confirmed it, say
  so, so a later session re-checks it.
- **Do not assume the owner knows.** Confirm or flag every loaded claim,
  especially about scope, cost, or what exists already.
- **No code in this stage.** Not even a stub.

## Completion criterion

Every fact is confirmed with a source or moved to an open item with a
resolution. The owner has said the decisions are theirs.
