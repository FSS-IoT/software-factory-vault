# Start here

You do not need to know how to program. You need an idea and an agent that can
read files and run commands.

Read this once. It is the first hour.

## 1. Install an agent

opencode, Claude Code, Codex, Cursor, Gemini CLI, anything that can open a folder
and edit files. The free tiers are enough to start.

## 2. Give it one sentence

From any folder, say:

> Clone `<the repo url>` and set up the software factory for me.

Or, if you already downloaded it: "I downloaded this folder, set it up for me."
Both are enough. The agent reads the vault and works out the rest.

## 3. Answer three questions

Whether you want one vault for everything (say yes), where it should live, and
which file your agent reads first. Pick somewhere permanent, like
`Documents/Vault`, not Downloads.

That one vault holds your projects, your machine notes, and the factory itself.
It is the part that makes an agent remember between sessions.

Then it proves the install by opening a fresh session in another folder and
asking where your vault is. If that works, you are done, and you never run setup
again.

## 4. Start a project by saying what you want

Open a folder for the project and say:

> I want to build a thing that does X.

That is the whole interface. It will write a brief, then interview you.

## 5. Answer badly, on purpose

Say what you want in your own words. Messy is right. You are not writing a
document, you are being interviewed.

It will fill in the brief, then ask you questions about it. Expect a wall of them
and answer in shorthand. **This is the most valuable hour of the project.**

Then it writes a spec, shows it to you, and waits. Read it. Fix what is wrong.
Say yes. That yes is the gate that stops it building the wrong thing.

## 6. Pick one milestone

The spec probably covers more than one. Take the smallest milestone that shows
something. If it is not detailed enough yet, the agent grills that too, then cuts
the tickets.

## 7. Watch one subticket end to end

The agent writes a check, runs it, and shows you it failing. Then the code that
makes it pass. Then a fresh session reviews it, and either approves it or sends
it back. Then it ships.

You are looking for two things:

- the check **failed before it passed** (if it never failed, it proves nothing)
- the reviewer found something, or explained what it checked

If there is nowhere to deploy yet, it stops at pushed and tells you.

## 8. Correct it

When the agent does something you dislike, say so. It writes the correction into
`PREFERENCES.md` and follows it next time. That is how this becomes your factory
instead of mine.

## What you should have after one lap

- `BRIEF.md` and `SPEC.md` in the project, with the spec signed.
- A page in `projects/` saying where the project lives and how it ships.
- One milestone with a handful of subtickets.
- One of them built, reviewed, and shipped.
- A `PREFERENCES.md` with at least one line that came from you.

If you have that, take the next subticket. If something about the method is wrong
for you, change it, and write the change in `CHANGES.md`.
