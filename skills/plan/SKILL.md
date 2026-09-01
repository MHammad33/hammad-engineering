---
name: plan
description: "Split approved design into tasks by working result, one build pass each. Use when work spans multiple build sessions. Skip for single-pass work (use build) or unapproved design (use design). Does not write code."
user-invocable: true
argument-hint: "<approved design path or feature name>"
---

# Plan

Turn approved design into tasks a fresh **build** agent can execute using only what design already decided. Split by working result, not by file or layer.

## How to work

**When to run this.** After **design** is approved and the change will take more than one **build** session. One session is enough → **build**. Nothing approved yet → **design**.

1. **Ground yourself.** Start from the approved design and the code it affects. When the repo has them, read `PROJECT.md` for product scope and `AGENTS.md` for commands and conventions. When they are missing, use the design plus what the human told you, and call out anything you still cannot verify (scope, how to test, repo habits) before listing tasks.

2. **Design owns decisions; plan owns order.** If a choice would change what the product does, how parts connect, what data crosses a boundary, or how you would verify the work, stop. Tell the human to resolve it in **design**. Do not bury open questions inside tasks.

3. **Slice by what works, not where it lives.** Each task should finish in one **build** pass and leave something that actually runs or behaves correctly, not a layer, folder, or file group.

4. **One place for each decision.** When two tasks would both need the same answer, combine that work or put it in the earlier task. If cleanup would disguise a behavior change, give it its own task.

5. **Put tasks in dependency order.** Label a milestone only when there is a real checkpoint (something to demo, review, or hand off), not for its own sake.

6. **Publish and stop.** Post the ordered task list in chat. Skip a plan file unless the human wants one. Do not **build**, **test**, or edit code. Your job ends at the list.

## Output

An ordered task list in chat:

```markdown
## Plan: <feature>

### Task 1: <title>
Goal:
Files likely touched:
Done when:
Depends on: none

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
