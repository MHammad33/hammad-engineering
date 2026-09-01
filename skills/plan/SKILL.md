---
name: plan
description: "Split approved design into tasks by working result — one build pass each. Use when work spans multiple build sessions. Skip for single-pass work (use build) or unapproved design (use design). Does not write code."
user-invocable: true
argument-hint: "<approved design path or feature name>"
---

# Plan

Turn approved design into tasks a fresh **build** agent can execute using only what design already decided. Split by working result, not by file or layer.

Use **plan** only after **design** is approved and the work needs more than one **build** pass. If one **build** is enough, use **build** directly. If design is missing or still open, use **design** first.

## Steps

1. Read the approved design, `PROJECT.md`, and project `AGENTS.md`.
2. Split work into ordered tasks. Each task should deliver working, verifiable behavior.
3. Note dependencies between tasks.
4. Keep tasks small enough for one **build** pass each.
5. Return the plan in chat unless the user asks for a file or tickets.

## Output

An ordered task list in chat:

```markdown
## Plan: <feature>

### Task 1: <title>
- Goal:
- Files likely touched:
- Done when:
- Depends on: none

### Task 2: <title>
...
```

## Human approval

Optional. Recommended for large plans. Ask if task order or scope looks wrong.

## Next

Execute tasks with **build**, then **test** after each task (or after a logical group).

Tell the human:

```text
Start with Task 1: Use the build skill. <task summary>
```
