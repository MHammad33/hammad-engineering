---
name: idea
description: "Challenge a vague own-product idea before any repo or code. Grills on gaps, writes IDEA.md, and recommends pursue, pivot, or kill."
argument-hint: "<your idea in one sentence, optional context>"
---

# Idea

Challenge an own-product idea and document enough clarity to decide whether to build it.

## Process

1. Read the request and any linked brief. Ask which scenario applies if unclear: own product, or learning/demo. Default to own product when the user might sell it. State what's already clear and what's missing.
2. Grill for what's missing — three to five focused questions per turn, waiting for answers before the next batch. Push back on a vague user, v1 scope creep, unbounded success claims, missing kill criteria, or builder motivation dressed up as user benefit. Mark anything you must assume as `[ASSUMPTION — confirm?]` — never state it as fact.
3. Keep going until every section below has a real, specific answer, not a placeholder. Then write `IDEA.md` in the human's working folder using the shape below.
4. End with a **Decision**: pursue, pivot, or kill, and why.
5. Give a short chat summary with the decision.

## IDEA.md shape

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
<!-- Primary user for v1. One person type, not a category. -->

## Product
<!-- What exactly is it? One sentence. -->

## How it works
<!-- 5–7 steps. User journey, no code. -->

## Why this might work
<!-- Why better than alternatives or doing nothing? -->

## Alternatives
<!-- What people do today instead. -->

## Money
<!-- Own product: who pays, for what, evidence. Learning / demo: write N/A. -->

| Question | Answer |
| --- | --- |
| Will someone pay? | yes / no / unknown |
| Model | |
| Value ≥ price | |
| First revenue | |

## Smallest useful version (v1)
<!-- Least we could build to learn or prove the idea. -->

## Out of scope (v1)
<!-- Feature exclusions and product behavior limits — refusals, access limits. -->

## Done when (seeds)
<!-- 3–5 observable checks — enough to write PROJECT.md's "Done when" later. -->

## Kill criteria
<!-- Concrete stop conditions, not vibes. -->

## Assumptions
<!-- Facts not confirmed by the human or brief. -->

## Decision
**pursue** | **pivot** | **kill**

Reason:
```

## Boundaries

- Client work with signed scope, an approved `PROJECT.md`, or an existing codebase — use the client path, **design**, or **understand** instead of this.
- Don't write `IDEA.md` on the first turn unless the human explicitly opts out of grilling.
- Don't fetch or read this repo's own docs, templates, or handoff links — those are for the human to open, not you.
- Don't suggest a stack, architecture, or hosting choice unless asked.
- Don't run **design**, **plan**, or **build**, or start `PROJECT.md` — the human handles the next stage.
- Don't recommend **pursue** while any section is still thin or a placeholder.
- A brief citation supports an answer — it doesn't prove it. Say "supported by," not "proven by."
- Skip a user story by default. Add one only if **Motivation** and **Problem** don't already make the behavior clear.

## Return

`IDEA.md`, and the decision in chat.

- **Kill** — stop, nothing else to do.
- **Pivot** — revise the idea and run **idea** again, or edit `IDEA.md` by hand.
- **Pursue** — tell the human to review `IDEA.md`, then open the [new project guide](https://github.com/MHammad33/hammad-engineering/blob/main/docs/new-project.md) and the [PROJECT.md template](https://github.com/MHammad33/hammad-engineering/blob/main/templates/PROJECT.md) themselves. Map **Done when (seeds)** → **Done when**, **Out of scope (v1)** → **Out of scope**, **Smallest useful version (v1)** → **v1 scope**.
