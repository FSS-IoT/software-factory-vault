---
name: Factory ship
description: >
  Commit, push, deploy by the project's recorded path, and prove it is live.
  Use after a subticket is approved. This is the stage that makes the work real.
---

# Ship

Scope: **one subticket**, after review approves.

Nothing is done until it can be opened. The loop that stops at "approved" is a
loop that never changes anything.

## Do

1. **Commit.** One subticket, one commit. The message says why, not what:
   "reject a wrong password, because the field kept the old value".
2. **Push.** To the branch the project uses. If the project uses branches and
   pull requests, this is where the pull request opens.
3. **Watch the checks** if the project has CI. A red pipeline stops the line,
   for everyone. CI is optional: without it, run the same checks by hand before
   you deploy, and say that you did.
4. **Deploy** the way this project deploys. The path is on the project's page,
   and it is the same path every time.
5. **Verify it is live**: open it, hit the endpoint, check the version. Not "the
   deploy command exited 0".
6. **Close the subticket** with the commit id, and update the project page if the
   deploy path or the live check changed.

If the project has nowhere to deploy yet, stop after the push and say so plainly.
Do not pretend a push is a release.

## The project page

The project's page records the four things this stage needs, and they do not
change from session to session. It is `<vault>/projects/<name>.md`, or a
`PROJECT.md` in the repo when the project is standalone:

- where the repository is
- the branch work lands on
- how it deploys, in one line
- how you know it is live

For a project with no deploy target: "deploys: nowhere yet, ships as a push". If
the path changes, update the page in the same session that ships the change.

## Rules

- **The same path every time.** A hand-made deploy is where factories quietly
  stop shipping.
- **Never ship red.** If the checks fail, the work goes back, not out.
- **Verify from the outside.** The machine that built it is not the machine that
  sees it.
- **Record the commit id** in the subticket, so the ticket points at the thing
  that shipped.

## Completion criterion

Committed, pushed, deployed if a deploy exists, verified live, subticket closed
with the commit id.
