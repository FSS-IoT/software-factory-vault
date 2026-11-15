# Glossary

Everything a beginner meets in the first hour, in one line each.

**Agent**: the program doing the work. It reads files, runs commands, and writes
code, following your instructions.

**Harness**: the app the agent runs inside. opencode, Claude Code, Codex, Cursor,
pi. It decides what the agent can touch and where it reads instructions.

**Vault**: a folder of markdown the agent reads and writes, so it remembers
between sessions. One general vault holds the projects, the notes, and the method
as subvaults.

**Subvault**: a folder inside the vault with its own `Home.md` and `AGENTS.md`,
indexed by the parent. The factory is one.

**Project page**: `projects/<name>.md`. Where the project lives, how it ships, and
what it holds to. The memory across sessions that the repo cannot be.

**Brief**: the project written down as facts, constraints and non-goals. Made
once, added to when the project grows.

**Session**: one conversation with the agent. It starts empty and forgets
everything when it ends, unless something was written to a file.

**Context window**: how much a session can hold at once. A subticket is sized to
fit in one, so the agent never loses the thread.

**Grill (grilling)**: the interview where the agent asks you questions until the
facts are settled. The cheapest place to be wrong.

**Spec**: the signed contract. What will be true, what will not, and how each
part will be checked.

**Milestone**: a group of work that ships together. Part of the spec, and the unit
your tickets belong to.

**Subticket (ticket)**: one idea, one check, one session. The smallest unit of
work that is still worth doing.

**Blocker**: a ticket that must finish before this one can start.

**Red**: writing the check and watching it fail, before any code exists.

**Green**: writing the smallest code that makes the check pass.

**Review (verify)**: a session with none of the author's context checking the
work against the spec. It can reject. It does not fix.

**Ship**: the milestone's closing move. Merge, deploy, prove it is live, close
the milestone.

**Repository (repo)**: the folder with its whole history attached. Every version
you ever committed is still there.

**Commit**: a snapshot with a message saying why it changed.

**Branch**: a parallel copy where one change is safe to try.

**Merge**: joining a branch back into the main line.

**CI**: a machine that builds the project and runs the checks on every push, so
"it worked on my machine" stops being an answer.

**Deploy**: putting the thing where users can reach it. The path you use is
written in the project page and never improvised.

**Station**: one of the four steps in the loop. The class handout uses this word
for tickets, red/green, review and ship.

**Preference**: a note about how you want the work done, kept in
`PREFERENCES.md`. Three of the same becomes a change to the method.
