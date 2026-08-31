---
name: build
description: "Implement the smallest complete change. Use when scope is clear, design is approved, or the task is a small decided fix."
user-invocable: true
argument-hint: "<task, plan item, or approved design path>"
---

# Build

Implement the requested change with minimal scope.

## When to use

- Clear task with known scope
- Approved **design** or **plan** task
- Small fix after **debug**
- Scaffolding a new project when `PROJECT.md` defines v1

## When not to use

- Root cause unknown (use **debug**)
- Important choices still open (use **design**)
- Behavior-preserving cleanup only (use **improve**)
- **Design** not yet approved

## Steps

1. Read the task, approved design or plan, `PROJECT.md`, and project `AGENTS.md`.
2. State what you will change in one short paragraph.
3. Implement the smallest complete change.
4. Follow existing project patterns. Do not refactor unrelated code.
5. Stop when implementation matches scope. Hand off to **test**.

## Output

- Code changes in the project
- Short summary of what changed and why

## Stop when

Implementation matches the approved scope.

Do not run full verification here. Use **test** next.

## Human approval

Required only if:

- Scope must expand beyond the design or task
- You need an architectural choice not already approved

Ask before expanding scope.

## Next

**test** — verify the change with evidence.

Example:

```text
Use the test skill. Verify the build changes against the acceptance criteria.
```
