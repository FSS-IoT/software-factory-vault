---
name: grill
description: >
  Verify facts before writing the spec: a grilling session that challenges each
  claim for a source. Use when you have a brief with facts and need them
  confirmed, or before any spec.
---

Grill the brief until every fact is confirmed. Facts before adjectives; a claim
without a confirmed source is an assumption, and assumptions do not enter the
spec.

## Method

For each fact in the brief, ask:
- **How do you know?** — require a source, a measurement, or a decision the
  owner makes now.
- **What is false if it is wrong?** — state the consequence so the owner feels
  the cost of being unverified.
- **Can it be verified now?** — if not, it becomes a grilling task, not a fact.

Present each as a challenge, not a question you already answered. Let the owner
confirm or correct.

## Output

Two lists:
- **Confirmed facts** — source named. These enter the spec.
- **Open items** — claims that could not be confirmed. Each with a resolution:
  verify further, drop it, or make it a non-goal.

## Rules

- **Do not assume the owner knows better.** Confirm or flag every loaded claim
  (scope, constraints, uncensored, sources).
- **Label inference.** If a fact is inferred rather than verified, mark it so a
  later reader re-verifies it.
- **Grilling is not asking permission.** It is buying certainty before code is
  written, so a wrong assumption is cheap.

## Completion criterion

Every fact in the brief is either confirmed with a source or moved to an open
item with a resolution. No unverified claim remains in the spec.
