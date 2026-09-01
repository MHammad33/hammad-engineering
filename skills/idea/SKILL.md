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
- You want motivation, user, money, and scope questions answered honestly

## When not to use

- Client work with signed scope — use the client path when available
- You already have an approved `PROJECT.md` — use **design** or **build**
- You are changing an existing codebase — use **understand** or **design**

## Steps

1. Read the request, any linked brief, and scenario. Ask which scenario applies if unclear: **own product** or **learning / demo**. Default to own product when the user might sell it. State what is already clear vs missing (gap scan).
2. Grill in chat using [Grill rules](#grill-rules). Follow [Writing rules](#writing-rules) and [Agent boundaries](#agent-boundaries).
3. Run the [Readiness checklist](#readiness-checklist). If any row fails, ask more questions.
4. Write `IDEA.md` in the human's working folder using [IDEA.md shape](#ideamd-shape). Apply Writing rules. Do not repeat facts across sections.
5. End with **Decision:** pursue, pivot, or kill — and why.
6. Give a short chat summary. If **pursue**, give the human-only handoff links below. Do not start `PROJECT.md` or read those URLs.

## Agent boundaries

These apply to **you** during ideation. They are not sections in `IDEA.md`.

- Do not write `IDEA.md` on the first turn unless the human explicitly opts out of grilling.
- Do not fetch or read Engineering Compass docs, templates, or handoff URLs — those links are for the human only.
- Do not suggest stack, architecture, hosting, or implementation choices unless the human asks.
- Do not run **design**, **plan**, or **build**.
- Do not invent answers. Mark `[ASSUMPTION — confirm?]` in chat when the human has not confirmed.
- Do not recommend **pursue** until the readiness checklist passes.
- Do not write `PROJECT.md`, create a repo, or continue past ideation — the human handles the next stage.

Product refusals, access limits, and safe-fallback behavior belong in **Out of scope (v1)** or **Done when (seeds)** in `IDEA.md`, not in this section.

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
2. **Ask; do not assume** for: scenario, motivation (user vs builder), primary user, problem, product, how it works, alternatives, v1, out-of-scope, done-when seeds, kill criteria, assumptions, and money (own product). An attached brief may answer some — still confirm gaps in chat.
3. **Batch questions.** Ask **3–5 focused questions** per turn. Wait for answers before the next batch.
4. **Push back** when you see:
   - vague user ("everyone", "businesses")
   - v1 scope creep (auth + admin + analytics in v1)
   - unbounded success ("works well", "reliable")
   - missing kill criteria or untestable done-when seeds
   - builder motivation mixed into user benefit without separation
5. **Label assumptions.** If the human has not answered and you must proceed, mark `[ASSUMPTION — confirm?]` in chat — never present assumptions as facts.
6. **Write `IDEA.md` only after** the readiness checklist passes or the human opts out of grilling.

Even with a full client brief, grill on items the brief typically leaves thin: **done-when seeds**, **kill criteria**, **assumptions**, and **out-of-scope edges**.

## Readiness checklist

Each row maps to one [IDEA.md](#ideamd-shape) section. Ideation is ready to write the file and recommend **pursue** only when every row passes.

| # | `IDEA.md` section | Ready when |
| --- | --- | --- |
| 1 | **Scenario** | own product or learning/demo stated |
| 2 | **Motivation** | User benefit and builder motivation separated |
| 3 | **Problem** | Specific pain, today, in plain language |
| 4 | **Users** | One concrete primary user (not a category soup) |
| 5 | **Product** | One sentence — what it is |
| 6 | **How it works** | 5–7 steps, no code |
| 7 | **Why this might work** | Clear vs alternatives or doing nothing |
| 8 | **Alternatives** | What people do today instead |
| 9 | **Money** | Answered (own product) or marked N/A (learning/demo) |
| 10 | **Smallest useful version (v1)** | Bullet list of must-haves |
| 11 | **Out of scope (v1)** | Explicit feature exclusions; include product behavior limits here when relevant |
| 12 | **Done when (seeds)** | 3–5 observable checks; include refusal or fallback cases when relevant |
| 13 | **Kill criteria** | Concrete stop conditions, not vibes |
| 14 | **Assumptions** | Listed separately from confirmed facts |

If any row is weak, keep grilling — do not write `IDEA.md` or recommend **pursue**.

After writing, add **Decision** with pursue, pivot, or kill and a reason.

## Ideation questions

Use these to grill. Map answers into the matching `IDEA.md` section. Tailor money for **learning / demo** (mark N/A).

**Why and who**

1. Why build this? (user benefit vs builder motivation)
2. Who is the primary user?
3. What problem do they have today?
4. What changes for them if this exists?

**What it is**

5. What exactly is the product? (one sentence)
6. How does it work? (5–7 steps, no code)
7. Why might this work better than what they use now?
8. What do people do today instead? (alternatives)

**Scope and proof**

9. What is the smallest useful version (v1)?
10. What is explicitly out of scope for v1?
11. What are 3–5 observable checks for done? (done-when seeds)
12. What would make us stop? (kill criteria)
13. What are we assuming that is not confirmed?

**Money (own product)**

14. Will someone pay for this? (yes / no / unknown)
15. Who pays, and for what?
16. How do they get value worth the price?

## IDEA.md shape

Write this file in the human's working folder after the readiness checklist passes. Fill every section.

```markdown
# Idea: <working title>

One-line description of what this might be.

## Scenario

<!-- own product | learning / demo -->

## Motivation

<!-- User benefit and builder motivation — separate them. -->

## Problem

<!-- Who hurts, how, and how often? One or two sentences. -->

## Users

<!-- Primary user for v1. One person type. -->

## Product

<!-- What exactly is it? One sentence. -->

## How it works

<!-- 5–7 steps. User journey, no code. -->

1.
2.
3.

## Why this might work

<!-- Why better than alternatives or doing nothing? -->

## Alternatives

<!-- What people do today instead. -->

-

## Money

<!-- Own product: who pays, for what, evidence. Learning / demo: write N/A. -->

| Question | Answer |
| --- | --- |
| Will someone pay? | yes / no / unknown |
| Model | |
| Value ≥ price | |
| First revenue | |

## Smallest useful version (v1)

-

## Out of scope (v1)

<!-- Feature exclusions and product behavior limits (refusals, access limits). -->

-

## Done when (seeds)

<!-- 3–5 observable checks — enough to write PROJECT.md "Done when" later. -->

-

## Kill criteria

<!-- Concrete stop conditions. -->

-

## Assumptions

<!-- Facts not confirmed by the human or brief. -->

-

## Decision

**pursue** | **pivot** | **kill**

Reason:
```

## Output

When the readiness checklist passes:

1. Write `IDEA.md` to the human's working folder using the shape above.
2. Apply Writing rules. Do not fetch external docs or URLs.
3. Deliver a short summary in chat with the decision.
4. Tell the human what to do next — use the table below. Links are **for the human to open**, not for you to read.

| Decision | Tell the human |
| --- | --- |
| **kill** | Stop. No next step. |
| **pivot** | Revise the idea and run **idea** again, or edit `IDEA.md` manually. |
| **pursue** | Review `IDEA.md`. When ready, open the [new project guide](https://github.com/MHammad33/hammad-engineering/blob/main/docs/new-project.md) and copy into the [PROJECT.md template](https://github.com/MHammad33/hammad-engineering/blob/main/templates/PROJECT.md). Map **Done when (seeds)** → **Done when**, **Out of scope (v1)** → **Out of scope**, **Smallest useful version (v1)** → **v1 scope**. |

## Stop when

`IDEA.md` is written, the decision is stated, and the readiness checklist passed before writing.

## Ideation rules

- Separate user benefit from builder motivation.
- If payment evidence is unknown, say so — pursuing to validate is OK with a tiny v1.
- Prefer the smallest v1 that tests the idea.
- Call out assumptions instead of hiding them.
