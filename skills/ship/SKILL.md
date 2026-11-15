---
name: Factory ship
description: >
  Close a milestone: when every subticket is reviewed, merge the work, deploy by
  the project's recorded path, prove it is live, and close the milestone. Use at
  the end of a milestone, not at the end of each subticket.
---

# Ship

Scope: **one milestone**, when every subticket in it is reviewed.

Shipping is the milestone's closing move. A milestone is done when its objectives
are complete and the thing is live. The objectives being complete does not mean
the software is perfect; it means everything agreed for this stage is done.

## Do

1. **Check the milestone.** Every subticket closed, each with its commit. Any
   still open is either finished now or moved to the next milestone, out loud.
2. **Merge** the work to the branch that is real.
3. **Watch the checks** if the project has CI. A red pipeline stops the line, for
   everyone. CI is optional: without it, run the same checks by hand before you
   deploy, and say that you did.
4. **Deploy** the way this project deploys. The path is on the project's page, and
   it is the same path every time.
5. **Verify it is live**: open it, hit the endpoint, check the version. Not "the
   deploy command exited 0".
6. **Close the milestone** with the commit range, and update the project page if
   the deploy path or the live check changed.

If the project has nowhere to deploy yet, stop after the merge and say so plainly.
Do not pretend a push is a release.

## Every ticket instead

Some projects deploy on each ticket: a live service with real users often should.
That is a preference, recorded in `PREFERENCES.md`, not a rule here. What the
method requires is that something ships, and that the person can see it.

## The project page

The page records the four things this stage needs. It is
`<vault>/projects/<name>.md`, or a `PROJECT.md` in the repo when the project is
standalone:

- where the repository is, and which branch is real
- how it deploys, in one line
- how you know it is live

For a project with no deploy target: "deploys: nowhere yet, ships as a push".

## Rules

- **The same path every time.** A hand-made deploy is where factories quietly
  stop shipping.
- **Never ship red.** If the checks fail, the milestone is not done.
- **Verify from the outside.** The machine that built it is not the machine that
  sees it.
- **Record the commit range** on the milestone, so the milestone points at the
  thing that shipped.

## Completion criterion

Merged, deployed if a deploy exists, verified live, milestone closed with the
commit range.
