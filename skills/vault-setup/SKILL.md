---
name: Vault setup
description: >
  Create or adopt the general vault that holds everything an agent learns: the
  index, the projects pages, the user and machine pages, and the software factory
  as a subvault. Use when someone says "set up a vault", "where should my notes
  live", or when the factory installer needs a vault that does not exist yet.
---

# Vault setup

A general vault is memory that outlives a session. One index, a few pages that
own their subjects, and the factory as one subvault among them.

Called by `skills/setup/` during an install. It builds the vault; **setup owns
the harness pointer and the handover.** If you are running this on its own, do
those two steps yourself when it is done.

## Modes

| Situation | Do |
|---|---|
| No vault yet | New, steps 1 to 4 |
| A vault exists | Adopt, steps 3 and 4 only, after asking |
| Standalone install, now wants a vault | Migrate, below, after steps 1 and 2 |
| The person does not want one | Stop. The factory runs standalone with a local `PROJECT.md`. |

Never restructure an existing vault without asking. A vault is someone's memory;
moving pages is how it stops being trusted.

## Migrating a standalone install

The factory was installed on its own and the owner now wants a vault. Do not
create a second copy of the factory, or the two will drift and neither will be
trusted.

1. Build the vault: steps 1 and 2.
2. **Move** the factory folder into `<vault>/software-factory/`, without its
   `.git`. Move, not copy. The vault's repository tracks it from now on.
3. Move each project's facts. A `PROJECT.md` in a repo becomes
   `<vault>/projects/<name>.md`, and the repo file becomes one line pointing at
   it, or is deleted if nothing links to it. Same facts, one owner.
4. Point the harness at the vault's `AGENTS.md` instead of the factory's
   `Home.md`. That is setup's step; do it in the same session if you are here on
   your own.
5. Tell the owner to start a new session. Every path the current one knows has
   moved underneath it.

## Step 1: the root

Pick a folder the person will remember, next to their projects rather than inside
one. `Documents/Vault` is a good default. Ask before creating anything.

Copy the skeleton from `templates/general-vault/` into it:

- `Home.md`, the index
- `AGENTS.md`, the contract for reading and writing
- `projects/`, `user/`, `system/`, each a subvault with its own `Home.md`,
  `AGENTS.md`, and one starter page

Then make it a git repository and commit, if git exists. Their memory should be
recoverable.

## Step 2: the categories

Ask which of these they want. All three is the answer for most people, and saying
so is not pushing:

- **`projects/`** one page per project. The one they will use most.
- **`user/`** how they like to work. Filled by correction, not by interview.
- **`system/`** this machine. OS, shell, editor, agent, paths, quirks.

Add a category by making the folder with a `Home.md` and an `AGENTS.md`, and
adding one line to the index in `Home.md`. Do not create empty categories "for
later"; they are where pages go to be forgotten.

A subject that is not a project gets its own folder only when it outgrows a
single page.

## Step 3: install the factory as a subvault

Copy the factory folder into the vault as `software-factory/`, without its `.git`
directory. The copy is the person's; the repository it came from is only a seed.

Add a line to the vault's `Home.md`:

| `software-factory/` | the method: the stages, templates, preferences |

If the vault already existed, that line is the whole install. Do not move or
rename anything else.

## Step 4: show it works

Prove the index before calling it done:

1. Open a session in a different folder.
2. Ask: "where is my vault, and what project pages does it have?"
3. The agent should read `AGENTS.md`, then `Home.md`, then answer.

If it cannot, the harness pointer is missing or wrong. That belongs to
`skills/setup/`; fix it there before finishing.

## Rules

- **Ask before writing.** Every folder, every page.
- **Copy, do not symlink.** A symlink breaks on the next machine and after a
  sync tool moves things.
- **Drop the seed's `.git`.** A nested repository inside the vault's own
  repository is a trap: the copy stops being tracked and nobody notices.
- **The index stays honest.** A page that is not in `Home.md` is a page nobody
  will read.
- **No secrets.** This folder is versioned.
- **Keep it small.** Three categories and one subvault is a finished vault. The
  rest is earned.

## Completion criterion

The vault has `AGENTS.md`, `Home.md`, the chosen categories, and the factory as a
subvault. Every page is in the index. A fresh session in another folder can find
it and name what is in it.
