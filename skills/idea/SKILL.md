---
name: idea
description: "Challenge a vague own-product idea before any repo or code. Asks ideation questions, writes IDEA.md, and recommends pursue, pivot, or kill."
user-invocable: true
argument-hint: "<your idea in one sentence, optional context>"
---

# Idea

Challenge an own-product idea and document enough clarity to decide whether to proceed.

## When to use

- You have a rough idea and are not sure it is worth building
- Before `PROJECT.md`, a repo, or any technical choices
- You want motivation, user, value, and money questions answered honestly

## When not to use

- Client work with signed scope — use the client path when available
- You already have an approved `PROJECT.md` — use **design** or **build**
- You are changing an existing codebase — use **understand** or **design**

## Steps

1. Read the request. Treat the argument as the idea unless a working title is given.
2. Ask which scenario applies if unclear: **own product** or **learning / demo**. Default to own product when the user might sell it.
3. Work through the ideation questions below. Recommend defaults when the user has not decided. Ask blocking questions only when the answer would change the recommendation.
4. Write `IDEA.md` locally (or in a notes folder). Use [`templates/IDEA.md`](../../templates/IDEA.md) sections.
5. End with an explicit **Decision:** pursue, pivot, or kill — and why.

## Ideation questions

Answer these in `IDEA.md`. Tailor money questions for **learning / demo** (mark revenue as N/A).

**Why and who**

1. Why build this?
2. Who is the primary user?
3. What problem do they have today?
4. What changes for them if this exists?

**What it is**

5. What exactly is the product? (one sentence)
6. How does it work? (5–7 steps, no code)
7. Why might this work better than what they use now?

**Money (own product)**

8. Will someone pay for this? (yes / no / unknown)
9. Who pays, and for what?
10. How do they get value worth the price?
11. What is the smallest useful version (v1)?
12. What would make us stop? (kill criteria)

## Output

Write `IDEA.md` with all sections filled and a final line:

```markdown
## Decision

**pursue** | **pivot** | **kill**

Reason: ...
```

Deliver a short summary in chat and point to the next step:

| Decision | Tell the human |
| --- | --- |
| **kill** | Stop. Do not open [new-project.md](../../docs/new-project.md). |
| **pivot** | Revise the idea and run **idea** again, or edit `IDEA.md` manually. |
| **pursue** | Open [new-project.md](../../docs/new-project.md) and write `PROJECT.md` from `IDEA.md`. |

## Stop when

`IDEA.md` is written and the decision is stated.

Do not run **design**, **plan**, or **build**. Do not suggest a tech stack unless the user explicitly asks.

## Rules

- Separate user benefit from builder motivation.
- If payment evidence is unknown, say so — pursuing to validate is OK with a tiny v1.
- Prefer the smallest v1 that tests the idea.
- Call out assumptions instead of hiding them.
