---
name: setup
description: >
  Guide setup of the Software Factory loop for a project: ask what is needed,
  where to save issues, and how to wire the memory store. Use when asked to
  install, set up, or configure the loop for a new project, or to onboard a
  starter.
---

Guide setup of the Software Factory loop for the project. It is a guided walk,
not a script: ask the questions, help the student choose, then the student does
the steps. No install scripts, no config files, no machine-specific commands.
It must work on any operating system the student has.

The goal is to get the student using a memory store for every project, whether or
not they knew one existed.

## Step 1 — What is needed

Ask what they are building and what the loop should do. Help them fill in:
- **Scope** — the milestone or first slice of work.
- **Constraints** — local-only, no paid APIs, no auth, uncensored, the stack they
  want.
- **Non-goals** — what this milestone does not do.

Then ask them to record those three in their own brief, the document they already
use to describe the milestone. The loop reads from that brief.

## Step 2 — Where to save issues

Ask where issues live. Three options:
- **Local scratch** — a folder with tickets and milestones, nothing shared.
  Simplest. The default for students.
- **GitHub issues** — a real issue tracker, PRs, CI.
- **Other** — GitLab, Gitea, or another tracker.

Walk them through the choice. Local scratch is fine if they have no remote. If
they pick a remote, help them connect their project to it — but ask first, and
never guess the project's settings.

## Step 3 — The memory store

Ask where to copy this methodology into, and whether they already have a store.

**They have none** — suggest creating one.
1. Pick a path for the main vault they can remember.
2. Copy this `software-factory` vault into it as a subvault.
3. Register the subvault in the main vault's index.
4. Register the main vault in their harness agents file (Step 4).

**They already have one** — ask whether they want this methodology inside it or
as a separate vault. If inside, copy it in as a subvault. If separate, copy it
to a new place and link it from their existing store.

A new store is not finished until it has a `Home.md`, its own repository
initialization, and a line in the root ignore so it is not tracked twice.

## Step 4 — The harness

Ask permission to add the memory store to the running agent's own harness, so the
agent and its agents find and create the store themselves when they need it.

The setup skill must not hardcode a path or command. It does not know the
harness. The agent that runs setup runs inside a harness and already knows how
to configure itself: discover the harness's own convention for agent
directions and config — how it reads agent instructions, where its config lives,
what its commands are — and add the pointer there using that mechanism. Do not
invent one.

The pointer should say:
- **The memory store** — where it lives, that it is a tiered structure, and the
  read-before-writing rule.
- **Default vaults** — suggest `Projects`, `User Preferences`, and one per
  shareable subject. Include these in the main harness instructions so new work
  lands in the right place.

## Suggested default vaults

Offer these as the starting points, and make sure they appear in the main
harness instructions:
- **Projects** — the repos worked on: clones, remotes, what each holds to.
- **User Preferences** — machine- and user-specific settings.
- **One per subject** — a subvault per shareable topic (methodology, a project,
  a service).

## Rules

- **Ask before writing.** Do not copy the vault or edit the harness file without
  confirmation.
- **No scripts, no config files, no machine commands.** The student does the
  steps by hand. Whatever the student's operating system, the walk is the same.
- **No project name, no stack, no remote baked in.** The setup is generic; the
  student records their specifics.
- **Keep it simple first.** A main vault and local scratch beat a complex
  structure. Grow the tiers only when they earn their place.

## Completion criterion

The student has a brief with scope, constraints and non-goals, an issue storage
chosen, a memory store in place, and — with permission — a pointer in their
harness agents file. They can start a milestone the next session without being
told where anything goes.
