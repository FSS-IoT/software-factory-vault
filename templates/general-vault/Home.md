# <owner>'s vault

One place for what agents learn, so it is not relearned every session.

An agent starts every session with no memory. A page in here is the memory.

## The rule

**Every fact lives in the page that owns its subject.** A fact with no page gets
one. A fact in two pages drifts.

- **Corrections go in the page they correct**, in the same session, not in a
  summary or a chat.
- **Link, do not duplicate.** One owner per fact; everything else points at it.
- **No secrets.** No tokens, passwords, or `.env` contents. This folder is
  versioned and may be pushed.
- **Write for the next session.** It has none of today's context.
- **Date what changes.** A state line with no date is a rumour.

## What is here

| Vault | Holds |
|---|---|
| `projects/` | one page per project: where it is, how it ships, what it holds to |
| `user/` | how the owner likes to work: tone, pace, tools, limits |
| `system/` | this machine: OS, shell, editor, agent, paths, quirks |
| `software-factory/` | the method: seven stages, templates, and its own preferences |

## Adding a vault

Make a folder with a `Home.md` of its own, then add a line to the table above.
Add one when a subject outgrows a single page. Before that, the page belongs in
an existing vault, and a new folder just gives it somewhere to hide.

## Where things go

- A new project starts in `projects/`, not in a chat.
- A preference the owner states twice goes in `user/`.
- A machine quirk that cost a pass goes in `system/`.
- How the work itself should run goes in `software-factory/PREFERENCES.md`.
