# Changes to the seed

What changed in this vault, so a copy that has drifted can see what it is missing
and a student can see why it looks the way it does.

Newest first. Method changes only. A preference belongs in `PREFERENCES.md`.

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
