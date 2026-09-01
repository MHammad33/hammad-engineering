---
name: idea
description: "Challenge a vague own-product idea before any repo or code. Grills on gaps, writes IDEA.md, and recommends pursue, pivot, or kill."
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

1. Read the request, any linked brief, and scenario. State what is already clear vs missing (gap scan).
2. Grill in chat using [Grill rules](#grill-rules). Follow [Writing rules](#writing-rules).
3. Run the [Readiness checklist](#readiness-checklist). If items fail, ask more questions.
4. Write `IDEA.md` using [`templates/IDEA.md`](../../templates/IDEA.md). No repeated facts across sections.
5. End with **Decision:** pursue, pivot, or kill — and why.
6. If **pursue**, tell the human the next step is `PROJECT.md` and which checklist items map directly to **Done when**.

## Writing rules

Apply to every chat reply during ideation and to the final `IDEA.md`.

- Use familiar words and specific verbs.
- When citing a brief or shared source, say the answer is **supported by** that document — do not claim to prove grounding or certainty.
- Do not add user stories by default. Add one only when it clarifies product behavior that **Motivation** and **Problem** do not already cover.
- Aim for **250 to 500 words** per chat response. Exceed 700 only when the extra text is required to prevent an unsafe or incompatible decision. Otherwise point to the shared source and ask a focused question.
- Do not repeat a fact in several sections of `IDEA.md`. Each section adds something new.
- Do not use slogans, metaphors, filler, or vague claims such as *robust*, *seamless*, *comprehensive*, or *future-proof*.

## Grill rules

Your job is to extract answers from the human, not to silently invent them.

1. **Gap scan first.** Before asking, list (briefly) what is already clear and what is missing.
2. **Ask; do not assume** for: primary user, problem, v1 boundaries, out-of-scope, kill criteria, and money (own product). An attached brief may answer some — still confirm gaps in chat.
3. **Batch questions.** Ask **3–5 focused questions** per turn. Wait for answers before the next batch.
4. **Push back** when you see:
   - vague user ("everyone", "businesses")
   - v1 scope creep (auth + admin + analytics in v1)
   - unbounded success ("works well", "reliable")
   - missing kill criteria or untestable done-when
   - builder motivation mixed into user value without separation
5. **Label assumptions.** If the human has not answered and you must proceed, mark `[ASSUMPTION — confirm?]` in chat — never present assumptions as facts.
6. **No stack or architecture** unless the human asks. Defer to **design**.
7. **Write `IDEA.md` only after** the readiness checklist passes or the human opts out of grilling.

**Hard rule:** On the first turn, do **not** write `IDEA.md` unless the human explicitly says to skip grilling and write from what exists.

Even with a full client brief, grill on items the brief typically leaves thin: **done-when examples**, **kill criteria**, **assumptions**, and **out-of-scope edges**.

## Readiness checklist

Ideation is ready for `IDEA.md` and **pursue** only when these are answerable without hand-waving:

| # | Item | Ready when |
| --- | --- | --- |
| 1 | **Scenario** | own product or learning/demo stated |
| 2 | **Primary user** | One concrete person type (not a category soup) |
| 3 | **Problem** | Specific pain, today, in plain language |
| 4 | **Product** | One sentence — what it is |
| 5 | **How it works** | 5–7 steps, no code |
| 6 | **v1** | Bullet list of must-haves |
| 7 | **Out of scope (v1)** | Explicit exclusions |
| 8 | **Done when (seeds)** | 3–5 observable checks a future **test** skill could verify |
| 9 | **Kill criteria** | Concrete stop conditions, not vibes |
| 10 | **Assumptions** | Listed separately from confirmed facts |
| 11 | **Money** | Answered (own product) or marked N/A (learning/demo) |
| 12 | **Decision** | pursue / pivot / kill with reason |

If any row is weak, keep grilling — do not write `IDEA.md` or recommend **pursue**.

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
| **pursue** | Open [new-project.md](../../docs/new-project.md) and write `PROJECT.md` from `IDEA.md`. Map **Done when (seeds)** into `PROJECT.md` **Done when**. |

## Stop when

`IDEA.md` is written, the decision is stated, and the readiness checklist passed before writing.

Do not run **design**, **plan**, or **build**. Do not suggest a tech stack unless the user explicitly asks.

## Rules

- Separate user benefit from builder motivation.
- If payment evidence is unknown, say so — pursuing to validate is OK with a tiny v1.
- Prefer the smallest v1 that tests the idea.
- Call out assumptions instead of hiding them.
