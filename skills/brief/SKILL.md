---
name: Factory brief
description: >
  Start a project. Turn a free-form idea dump into a brief with facts,
  constraints and non-goals, so the interview has something to attack. Use at the
  very start of a project, before any spec exists.
---

# Brief

Scope: **project**, once. A milestone does not get its own brief.

The owner talks, you write. They do not need to be organised, complete, or
technical. Your job is to get what is in their head onto the page without
tidying it into something they did not say.

## Ask for

- **The idea**, in one sentence, in their words.
- **Who it is for**, and where they will use it.
- **What it must do**, and what it must never do.
- **What it has to work with**: existing systems, accounts, hardware, policy.
- **What "done" looks like** for the first version.
- **Two things they like and two they hate**, with names. That is how taste gets
  recorded without adjectives.
- **What already exists.** A folder, a spreadsheet, a person doing it by hand.

Then write `BRIEF.md` in the project root, from `templates/brief.md`. Keep it
under a page.

## Where the project lives

Four facts belong on one page, `PROJECT.md`, from `templates/project.md`:

- where the repository is, or "not created yet"
- which branch work lands on
- where tickets live: local files, GitHub issues, or another tracker
- how it deploys, in one line, or "nowhere yet, ships as a push"

Ask for them here, once. Every later stage reads this page instead of asking
again. A project with no repo and no deploy target is normal at the start; write
that down honestly instead of inventing an answer.

## Rules

- **Facts before adjectives.** "Loads in under a second on the office wifi" is a
  fact. "Fast and modern" is an adjective: put it in non-goals or make it a
  grilling task.
- **Every fact carries where it came from**, or is marked as a grilling task.
- **Non-goals are load-bearing.** A project that does not say what it will not do
  will do more.
- **No stack, no tool, no language.** Behavior only. The implementation is a
  choice for later.
- **An existing brief is not rewritten.** Adding a milestone means adding to it.

## Completion criterion

`BRIEF.md` exists with facts, constraints and non-goals, and `PROJECT.md` records
where the code, the tickets and the deploy live. Anything unconfirmed is listed
for the grill. The owner has read the brief and said it is right.
