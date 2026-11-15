# Start here

You do not need to know how to program for this. You need an idea and an agent
that can read files and run commands.

Read this once. It is the first hour.

## 1. Install an agent

opencode, Claude Code, Codex, Cursor, Gemini CLI, anything that can open a folder
and edit files. The free tiers are enough to start.

## 2. Put this vault somewhere you will remember

Keep it next to your projects, not inside one. Something like
`Documents/factory`. Ask your agent to copy it there if you would rather not.

## 3. Tell your agent where it is

Say this to your agent, once:

> The software factory method lives at `<path>/Home.md`. Read it before planning
> or starting work. Set the factory up for me from `skills/setup`.

The agent reads `Home.md`, so you do not have to explain the method to it. If it
asks where the vault is, paste the path.

## 4. Answer the setup questions

It will ask a few things: what you are building, where tickets should live, and
where the finished thing goes when it is live. Plain answers are fine. "I don't
know yet" is also an answer, and it will be written down as one.

## 5. Give it your idea, badly

Say what you want in your own words. Messy is right. You are not writing a
document, you are giving an interview.

It will fill in a brief, then interview you about it. Expect a wall of questions
and answer in shorthand. **This is the most valuable hour of the project.**

Then it writes a spec, shows it to you, and waits. Read it. Fix the parts that
are wrong. Say yes. That yes is the gate that stops it building the wrong thing.

## 6. Pick one milestone

The spec probably covers more than one milestone. Take the smallest one that
shows something. If that milestone is not detailed enough yet, the agent grills
that too, and then cuts the tickets.

## 7. Watch one subticket end to end

The agent writes a check, runs it, and shows you it failing. Then it writes the
code that makes it pass. Then a fresh agent reviews the work and either approves
it or sends it back.

You are looking for two things:

- the check **failed before it passed** (if it never failed, it proves nothing)
- the review agent found something, or explained what it checked

Then it ships. If there is nowhere to deploy yet, it stops at pushed and says so.

## 8. Correct it

When the agent does something you do not like, say so. It writes that correction
into `PREFERENCES.md`, and follows it next time. That is how this becomes your
factory instead of mine.

## What you should have after one lap

- `BRIEF.md` and `SPEC.md` in the project, signed.
- One milestone with a handful of subtickets.
- One of them built, reviewed, shipped.
- A `PREFERENCES.md` with at least one line that came from you.

If you have that, run the next subticket. If something in the method is wrong
for you, change it, and write the change in `CHANGES.md`.
