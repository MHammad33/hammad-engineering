---
name: build
description: "Implement the smallest complete change. Use when scope is clear, design is approved, or the task is a small decided fix."
argument-hint: "<task, plan item, or approved design path>"
---

# Build

Implement the requested change with minimal scope.

## Process

1. Read the task, the approved design or plan, `PROJECT.md`, and project `AGENTS.md`.
2. State what you're about to change, in one short paragraph.
3. Implement the smallest complete change. Follow existing project patterns.
4. Stop once implementation matches scope.

## Boundaries

- Root cause unknown — use **debug** first, not this.
- Important choices still open — use **design** first, not this.
- Behavior-preserving cleanup with no feature — use **improve** instead.
- Don't refactor unrelated code.
- Don't expand scope, or make an architectural choice not already approved, without asking first.
- Don't run full verification here — that's **test**.

## Return

Code changes, and a short summary of what changed and why. Hand off to **test**: "Use the test skill. Verify the build changes against the acceptance criteria."
