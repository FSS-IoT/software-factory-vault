# Preferences

How this owner wants the work done. The agent reads this before it plans
anything, and it wins over the stage files where the two disagree.

This file is only about running the factory. Broader preferences (tone, tools,
what they are learning) belong to the general vault's `user/preferences.md` when
there is one, and the two link to each other.

## How a line gets here

- **A correction becomes a line.** When the owner says "do it this way instead",
  the agent appends one line below, in the owner's words, with the date. No
  rewrite, no interpretation.
- **Three times becomes the method.** The same correction appearing three times
  is a proposal, not a note: the agent suggests an edit to the stage file, shows
  the diff, and the owner decides. Then the three lines collapse into one.
- **A method change is not a preference.** The stage order, the gates, or a
  missing stage go in the stage file and get a line in `CHANGES.md`. Anything
  about taste, pace, tools or ceremony belongs here.

## Machine and harness

Recorded once at setup, and changed whenever the machine or the harness changes.
The method does not depend on it, but the review stage needs to know.

- Harness:
- Model: hosted / local (which one)
- Two contexts at once: yes / no
- Review runs as: subagent / new session / second harness

If you move from a local model to a hosted one, or install a subagent module,
change the last line. That is the whole migration.

## What belongs here

- How much ceremony: "small changes skip tickets", "always cut tickets".
- How work is split: "one commit per subticket", "red and green in one session".
- When it ships: "every milestone" (the default) or "every ticket".
- Where things live: "issues in GitHub", "notes in this vault", "no CI".
- Voice: "explain the check before running it", "no summaries at the end".
- Anything the owner has corrected twice.

## What does not

- Project facts. Those go in the project's `BRIEF.md` and `SPEC.md`.
- Secrets, tokens, or paths that only exist on one machine.

---

_Nothing yet. The first correction lands here._
