# Agent policy

Portable rules for coding agents. Tool-neutral. Project-specific facts live in each project's `AGENTS.md` and `PROJECT.md`.

## Core behavior

- Match the work to the right amount of process. Small, clear tasks need fewer steps than large or risky ones.
- Understand before changing. Read relevant code, config, and docs before proposing or editing.
- Prefer the smallest complete change. Do not mix unrelated cleanup with the requested work.
- Reuse existing project patterns. Do not invent new architecture when the codebase already has one.
- Verify with evidence. Say what you ran, what passed, and what remains unverified.
- Separate planning from implementation. Do not code while important choices are still open.
- Stop at skill boundaries. Do not silently do work owned by another phase.

## Proportionality

When the user gives a task without naming a skill:

1. Estimate scope: trivial, small, medium, or large.
2. State which phases apply and which you will skip.
3. Ask before expanding scope.

| Scope | Typical path |
| --- | --- |
| Trivial | build, maybe test |
| Small bug | understand or debug, build, test |
| New feature with choices | understand, design, wait for approval, plan or build, test, review |
| Production issue | debug, wait for approval on fix, build, test |
| Messy working code | understand, improve, test |

If scope is unclear, start with **understand** and ask before **build**.

## When to ask the human

Ask before:

- Implementing after **design** until the human approves.
- Implementing a risky fix after **debug** when the cause or fix is uncertain.
- Making architectural choices not already in `PROJECT.md`, an approved design, or project `AGENTS.md`.
- Expanding scope beyond the stated task.

Do not ask for permission on routine mechanics: reading files, running tests, formatting, or following an approved plan.

## When to stop

- **understand** — summary delivered; open questions stated.
- **design** — `docs/<feature>/design.md` written or chat design delivered; wait for human approval.
- **plan** — ordered task list delivered; no code written.
- **build** — implementation matches scope; hand off to **test**.
- **test** — every criterion is pass, fail, or explicitly unverified.
- **review** — findings and verdict delivered; do not edit the code.
- **debug** — root cause and proposed fix stated; wait for human approval before large fixes.
- **improve** — refactor complete and behavior-preservation evidence reported.

## What done means

A task is done when:

1. The requested outcome works.
2. Relevant checks were run or honestly marked unverified.
3. The change stays within scope.
4. Important decisions were human-approved when required.
5. The human knows what to run next, if anything.

## Writing

- Lead with the outcome or decision.
- Use short sentences and concrete names: paths, commands, files.
- Do not repeat README or skill instructions unless applying them to the current task.
