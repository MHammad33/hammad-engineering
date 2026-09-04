---
name: understand
description: "Build an accurate picture of relevant code before changing it. Use when starting a task in unfamiliar code, or before design on a non-trivial change."
argument-hint: "<task, area, or question>"
---

# Understand

Learn how the relevant part of the system works before proposing or changing it.

## Process

1. Read the request and anything linked — files, errors, docs, `PROJECT.md`, project `AGENTS.md`, existing designs.
2. Read the relevant code paths. Trace behavior end to end where it matters.
3. Note existing patterns, conventions, and dependencies.
4. List affected files and boundaries.
5. State open questions that block safe work.

## Boundaries

- Don't use this when the user already pointed to an exact one-line change — go straight to build.
- Don't re-run this on ground already covered this session, if nothing's changed.
- Don't write a file unless asked. This stays in chat.

## Return

A short chat summary: what exists today, what the task affects, patterns to follow, and open questions.

Open questions that block safe work — ask before continuing. Otherwise: a non-trivial change with open choices goes to **design**; a clear fix goes to **build** or **debug**; an unknown failure goes to **debug**.
