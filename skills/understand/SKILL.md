---
name: understand
description: "Build an accurate picture of relevant code before changing anything. Use when starting a task, entering unfamiliar code, or before design."
user-invocable: true
argument-hint: "<task, area, or question>"
---

# Understand

Learn how the relevant part of the system works before proposing or changing it.

## When to use

- Starting a task in unfamiliar code
- Before **design** on a non-trivial change
- When you need to know what files and patterns are involved

## When not to use

- The user pointed to an exact one-line change
- You already explored this area in the current session and nothing changed

## Steps

1. Read the request and any linked files, errors, or docs (`PROJECT.md`, project `AGENTS.md`, existing designs).
2. Read the relevant code paths. Trace behavior end to end when needed.
3. Note existing patterns, conventions, and dependencies.
4. List affected files and boundaries.
5. State open questions that block safe work.

## Output

A short summary in chat:

- What exists today and how it works
- What is affected by the task
- Relevant patterns to follow
- Open questions (if any)

Do not write a file unless the user asks for one.

## Stop when

The summary is delivered and blocking questions are stated.

## Human approval

Not required unless you find major ambiguity or conflicting patterns. Ask before proceeding to **build**.

## Next

| Situation | Next skill |
| --- | --- |
| Non-trivial change with open choices | **design** |
| Clear fix or small change | **build** or **debug** |
| Unknown failure | **debug** |
| Open questions block work | Ask the human |
