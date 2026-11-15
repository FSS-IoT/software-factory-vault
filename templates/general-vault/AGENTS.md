# vault contract

Read `Home.md` first, then the page that owns the subject. This file says how to
read and write the vault, not what is in it.

## Read

- `Home.md` for the index.
- The page that owns the subject. Not a neighbouring page that mentions it.
- `software-factory/PREFERENCES.md` before planning work on a project.

## Write

- **A fact goes in the page that owns it.** No page yet? Make one, and add it to
  the index in `Home.md` in the same edit.
- **A correction is load-bearing.** When the owner says something here is wrong,
  fix the page before the session ends. A stale page is worse than a missing one,
  because it gets trusted.
- **Link, do not duplicate.** If two pages need the same fact, one owns it and the
  other links to it.
- **No secrets.** No tokens, passwords, keys, or `.env` contents, ever.
- **Date what changes.** State lines carry the date they were true.

## Where things go

| The fact | The page |
|---|---|
| What a project is, where it lives, how it ships | `projects/<name>.md` |
| How the owner wants to work | `user/preferences.md` |
| This machine's setup and quirks | `system/machine.md` |
| How the factory runs, stage by stage | `software-factory/` |

If it does not fit one of those, it belongs in the page that owns the subject, and
that page may be new.
