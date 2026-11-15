# Changes to the seed

What changed in this vault, so a copy that has drifted can see what it is missing
and a student can see why it looks the way it does.

Newest first. Method changes only. A preference belongs in `PREFERENCES.md`.

## 2026-11-15, later

The brief is not a station, and ship closes the milestone.

- **Starters split from the loop.** Brief, research, grill and spec produce the
  plan once per project. They are not stations; the loop is tickets, red/green,
  review and ship, run on every milestone.
- **Research is the optional starter.** For ideas that depend on facts nobody has
  yet, research writes them into the vault before the grill, so the interview does
  not start by guessing.
- **Ship moved to the milestone.** Approval closes the ticket, with its commit.
  Ship merges, deploys, verifies and closes the milestone. A milestone being
  complete means its objectives are done, not that the software is perfect.
- **Shipping every ticket is a preference.** Some projects deploy per ticket, and
  micahn does. The default here is per milestone because it is easier to teach;
  the copy is the owner's to change.

## 2026-11-15

A general vault, and the factory as one subvault of it.

- **`skills/vault-setup/` added.** It builds or adopts the vault that holds the
  owner's memory: `Home.md`, `AGENTS.md`, and `projects/`, `user/`, `system/`.
  `templates/general-vault/` is the skeleton it copies, so a weak agent copies
  files instead of inventing a structure from prose.
- **Setup chooses a mode**: new vault, existing vault, or standalone. It no
  longer assumes the factory is the whole store.
- **Project facts move out of the repo** when a vault exists: the page is
  `projects/<name>.md`, and the repo keeps only `BRIEF.md` and `SPEC.md`. With no
  vault, the question is asked once and `PROJECT.md` stays beside the code.
- **The harness pointer now aims at the vault's `AGENTS.md`**, which points at
  `Home.md`, which points at the subvault. One line, then links do the rest.
- **The ship stage updates the project page** when the deploy path or the live
  check changes, so the page is the live truth and not a first-day snapshot.
- **Standalone can become a vault later.** `skills/vault-setup/` now migrates: move
  the seed in rather than copying it, move each `PROJECT.md` to
  `projects/<name>.md`, repoint the harness, start a new session. Nothing is
  reinstalled.
- **Two preference files, on purpose.** The factory's own is
  `software-factory/PREFERENCES.md`; the person's broader preferences are
  `user/preferences.md`. They link to each other and neither owns the other's
  facts.

## 2026-11-15

Setup is an installer, not a stage.

- **Setup moved out of the loop.** It ran once as "step 0", which made it look like
  a station. It now installs the method and hands over; the loop starts when the
  owner says what they want to build.
- **Entry is natural language.** Home has a table from what a person says ("set up
  the factory", "I want to build X", "ship it") to the file to read. An agent that
  has read Home routes itself.
- **Setup works from anywhere.** Cloned, downloaded, unpacked, run from home or a
  scratch folder, on any OS. It places the vault permanently, adds the pointer to
  the global instruction file, and proves it from a different folder before
  handing over.
- **Project facts moved to `PROJECT.md`**, written by the brief stage: repo,
  branch, where tickets live, how it deploys. Ticket storage is no longer a global
  install question.
- **CI/CD is optional machinery.** The ship and verify stages now say it: a
  pipeline can run beside the loop or take over the mechanical half of review
  (does it build, do the checks pass, did anything else break), and it cannot make
  the judgment. A project without CI ships the same way, by running the same checks
  by hand and saying so.

## 2026-11-14

Restructured before the first class. The loop is the same; the front door and the
back door were missing.

- **Two levels.** Brief and spec are project documents. Tickets and everything
  after them are per milestone. The old version implied one lap per project.
- **Grilling is a move, not a stage.** It runs at project start, on a milestone
  that has no subtickets, or on a topic. Previously it only sat between brief and
  spec.
- **`red` and `green` merged into `redgreen`.** One session, one invocation. The
  old split cost three skill calls per ticket, and the owner's own tickets carry
  both checklists anyway. Also avoids the opencode Build agent.
- **`review` renamed to `verify`.** opencode's `/review` command reviews a diff in
  the current session, which is the opposite of a fresh reviewer. The stage keeps
  the name Review in prose; the file is `skills/verify/`.
- **`ship` added.** Commit, push, deploy by the recorded path, verify live. The
  method used to stop at "approved", which is not shipped.
- **Setup rewritten.** It was two drafts stapled together, with duplicated steps
  and a harness section that contradicted the discovery section. Now one ordered
  walk, ending in one real subticket.
- **The install is a pointer.** One line in the harness's global instruction file.
  Nothing is copied into a skills folder, and nothing requires installation.
- **`PREFERENCES.md`, `START-HERE.md`, `GLOSSARY.md` added.** The vault can now
  learn how its owner works, and a beginner has somewhere to start.
- **Templates fixed.** Brief, spec and project added. The subticket template now
  records the failing run, the verdict and the commit, instead of placeholders for
  a folder that never existed.
