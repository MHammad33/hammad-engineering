---
name: design
description: "Decide what to build and how before coding. Use for features, interfaces, data, security, or non-trivial changes. Writes docs/<feature>/design.md and waits for approval."
user-invocable: true
argument-hint: "<feature, problem, or PROJECT.md context>"
---

# Design

Settle important product and technical choices before implementation.

## When to use

- New feature or meaningful behavior change
- Multiple valid approaches exist
- Interfaces, data, auth, security, or operations need decisions
- The change spans several files or components

## When not to use

- Obvious bug with clear fix
- Rename, typo, or config tweak
- Constraints and v1 scope are already fully settled in `PROJECT.md`

## Steps

1. Read the request, `PROJECT.md`, project `AGENTS.md`, relevant code, and prior **understand** output.
2. Identify decisions implementation must not invent silently.
3. Ask blocking questions only when the answer would change the design. Recommend a default.
4. Write the design:
   - **Default:** `docs/<feature-slug>/design.md` in the project repo
   - **Small change:** chat-only design is OK if the user prefers
5. Tailor sections to the task. Include only what matters.

## Design document sections

Use these headings. Omit sections that do not apply.

```markdown
# <Title>

> Status: Proposed — awaiting approval

## Summary
What changes, for whom, and the main tradeoff.

## Context
Current behavior and why it is insufficient.

## Proposed approach
How it works end to end.

## Decisions
What you chose, what you rejected, and why.

## Requirements
Testable behavior and constraints.

## Invariants
Rules that must not break (when relevant).

## Error behavior
Important failure paths (when relevant).

## Test strategy
How to verify acceptance criteria.

## Out of scope
What this design does not include.

## Open questions
Unresolved items and whether they block implementation.
```

## Stop when

The design is written and ready for review.

**Wait for explicit human approval.** Do not run **plan** or **build** until the human confirms or requests changes.

## Human approval

**Required.** Stop and ask: "Please review the design. Reply approved or request changes."

## Next

After approval:

| Situation | Next skill |
| --- | --- |
| Several steps or sessions | **plan** |
| One clear implementation pass | **build** |

Tell the human:

```text
When approved, run plan (multi-step) or build (simple).
```
