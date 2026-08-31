---
name: plan
description: "Split approved work into ordered, agent-ready tasks. Use after design approval when work needs more than one focused pass. Does not write code."
user-invocable: true
argument-hint: "<approved design path or feature name>"
---

# Plan

Break approved work into ordered tasks an agent can execute one at a time.

## When to use

- Approved **design** with multiple steps
- Work that will span several agent sessions
- Dependencies exist between pieces of work

## When not to use

- Single-step change with a clear path
- No approved design or clear scope yet
- Trivial task where planning adds no value

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

## Stop when

The task list is complete. No code is written.

## Human approval

Optional. Recommended for large plans. Ask if task order or scope looks wrong.

## Next

Execute tasks with **build**, then **test** after each task (or after a logical group).

Tell the human:

```text
Start with Task 1: Use the build skill. <task summary>
```
