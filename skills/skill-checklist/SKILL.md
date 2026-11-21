---
name: skill-checklist
description: A yes/no checklist for writing or reviewing a skill for an AI agent, built on ideas from The Pragmatic Programmer. Use when writing a new skill, reviewing or fixing an existing one, or after an agent misread, skipped or wrongly loaded a skill. Works in any project.
---

# Skill checklist

A skill is code written in English for an agent. The rules for good code carry over: keep each fact in one place, give each part one job, start small, fix small problems fast, and stop on bad input. Every item below is a check you can answer yes or no.

## Keep each fact in one place (DRY)

- [ ] Each rule lives in one skill. Other skills link to it with `[[skill-name]]` instead of copying it.
- [ ] Facts the code or config already holds (versions, paths, commands) are pointed to, not copied.

Why: copies drift apart. When two skills disagree, the agent follows whichever it read last.

## Give each skill one job (orthogonality)

- [ ] The skill's purpose fits in one sentence without "and".
- [ ] The `description` says what the skill does, then "Use when ..." with the tasks and phrases that should load it.
- [ ] Where a neighbouring skill could also match, the `description` says which tasks belong to the other one.
- [ ] Changing this skill doesn't force a change in another skill.

Why: when two skills overlap, the agent loads the wrong one, or both.

## Say what goes in and what done looks like (design by contract)

- [ ] The skill says what the agent needs before it starts: inputs, files, tools.
- [ ] It says what "done" looks like, as a check the agent can run or see (tests pass, file exists, PR link given).

Why: without a clear finish line, the agent stops too early or keeps going too long.

## Stop rather than guess (crash early)

- [ ] The skill says when to stop and ask the user instead of guessing.
- [ ] If a needed file, tool or input is missing, the agent is told to say so, not work around it.
- [ ] Steps that are hard to undo or reach other people (delete, push, send, publish) need the user's go-ahead.

Why: an agent that guesses and carries on causes damage that is hard to find later.

## Start small and try it (tracer bullets)

- [ ] The first version is the smallest one that does the job from start to finish.
- [ ] It was tried on a real task in a fresh session, and the agent loaded it without being told to.
- [ ] Each later rule was added because a real task showed it was needed.

Why: a long skill written up front is mostly guesses, and the guesses bury the rules that matter.

## Fix it the first time (broken windows)

- [ ] When an agent misreads or skips the skill, the wording or the trigger is fixed that day.
- [ ] Stale paths, names and commands are fixed or cut, never left with "may be out of date".

Why: one wrong line teaches the agent to doubt the rest of the skill.
