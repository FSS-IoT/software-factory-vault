---
name: Factory setup
description: >
  Set the factory up for a person: find their harness, place the vault, add one
  pointer, choose where tickets and deploys go, then prove the loop with one real
  subticket. Use for a first install, or when onboarding someone new.
---

# Setup

Scope: **once per person**. After this, the loop runs on its own.

You are walking a person through it, not installing software. They may have never
opened a terminal. Ask before writing anything, and explain each step in one
sentence before doing it.

## Done looks like

- The agent reads this vault at the start of every session.
- One place for tickets, one way to deploy, both written down.
- One project with a signed spec and one subticket that shipped.
- `PREFERENCES.md` has at least one line in the owner's words.

## Step 0: which harness

| Harness | Instruction file it reads first | Skills folder |
|---|---|---|
| opencode | `~/.config/opencode/AGENTS.md` | `~/.config/opencode/skills` |
| Claude Code | `~/.claude/CLAUDE.md` | `~/.claude/skills` |
| Codex, many CLIs | `AGENTS.md` in the project | none |
| Cursor | `.cursor/rules` | none |
| Gemini CLI | `GEMINI.md` | none |

If theirs is not listed, ask it directly: "which file do you read at the start of
every session?" Use what it answers. Never invent a path.

Subagents are a capability, not a requirement. Ask two questions and record the
answers in `PREFERENCES.md`: does this harness have subagents (on some, like pi,
they are a separate module), and can this machine run two contexts at once? A
review as a new session is just as valid as a review as a subagent. Nothing in
the method depends on running two things at the same time.

## Step 1: place the vault

Ask where it should live. Next to their projects, not inside one. Something like
`Documents/factory` is fine.

If this vault is already on their machine, keep it where it is. If not, copy it
there and ask them to look at the folder, so they know where it is.

Then make it a git repository, so their edits are recoverable. If they have never
used git, offer to run it for them and show the output. Do not assume a shell.

## Step 2: the pointer

Add this to the instruction file from Step 0, in the **global** file, never the
project one, because project instruction files get regenerated:

> The software factory method lives at `<path>/Home.md`. Read it before planning
> or starting work. When a stage needs doing, open its file in `skills/`.

One line. This is the whole install. Nothing is copied into a skills folder.

## Step 3: exposing the stages (optional)

Leave this out unless they ask for `/grill` style commands.

The vault works without it. If they want the stages visible in the harness's own
skill list, either add the vault's `skills` folder as a skills source (opencode:
a `skills` entry in `opencode.json`), or link the folder in. Link or configure
the single copy; do not make a second copy to maintain.

Two names in the vault are deliberately not the harness's words:

- **`redgreen`**, because opencode has a Build agent.
- **`verify`**, because opencode has a `/review` command that reviews a diff in
  the current session, which is not this stage.

Tell them that once. It stops the obvious wrong turn.

## Step 4: where tickets live

Three options. Recommend the first unless they already have a tracker.

- **Local files**: simplest, no account, works offline. One folder per milestone.
- **GitHub issues**: a real milestone, one issue per subticket, blockers between
  them.
- **Other tracker**: GitLab, Gitea, Jira. Same shapes, different names.

Write the choice in `PROJECT.md`. Do not change it mid-project.

## Step 5: how it ships

Ask where the finished thing goes when it is live. They may not have an answer,
and that is allowed: record "nowhere yet, ships as a push".

Write it in `PROJECT.md` as one line. This is what the ship stage follows, and it
is the difference between a project and a folder of files.

## Step 6: the first project

Do this together, with their real idea.

1. Brief (`skills/brief/`). They talk, you write.
2. Grill (`skills/grill/`). Interview them. This takes the longest, and it is the
   most valuable part of the install.
3. Spec (`skills/spec/`). One screen, then wait for the signature.

Stop after the signature. Do not build anything yet.

## Step 7: prove the loop

Take the smallest subticket that does something visible.

Run it start to finish: red, green, verify, ship. Do not skip verify, and do not
let the verifying session be the one that wrote the code.

Then ask two questions: what did the owner dislike, and what would they do
differently? Write the answers in `PREFERENCES.md`. That is the first line of
their factory rather than yours.

## Rules

- **Ask before writing.** Every file, every config line.
- **No machine-specific commands.** If a step needs one, offer to run it and show
  the output. Never assume the shell, the OS, or the package manager.
- **No project specifics in the vault.** Their project goes in `PROJECT.md`, their
  taste in `PREFERENCES.md`.
- **Keep it small.** A single vault and local ticket files beat a structure with
  tiers they did not ask for.
- **Do not install what they did not ask for.** The pointer is the install; the
  rest is optional.

## Completion criterion

The owner can start their next milestone without you, and knows where their
preferences, tickets, and deploy path are written down.
