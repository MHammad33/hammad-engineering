# New idea

Step-by-step guide for an **own-product** idea you have not validated yet. Do each step in order. No repo and no code until Step 3.

Client work uses a different path — coming later.

Open this guide from the [README](../README.md) when you have a rough idea and want to know if it is worth building.

---

## Before you start

You need a rough idea — even one sentence. You do not need a repo, stack, or `PROJECT.md`.

**Example idea:** "Let's build a customer support agent."

---

## Step 1 — Use the idea skill

**Do**

1. Install skills if you have not yet — [install.md](install.md).
2. Run the **idea** skill with your idea in one sentence.

**Example prompt**

```text
Use the idea skill. Let's build a customer support agent for small e-commerce shops.
```

**What happens**

The agent works through ideation questions and writes **`IDEA.md`** (use [`templates/IDEA.md`](../templates/IDEA.md)). It covers:

- Why build this, and for whom
- What the product is and how it works
- Whether anyone might pay, and how
- The smallest useful v1
- When to stop (kill criteria)

It does **not** pick a tech stack, create a repo, or write code.

**Brief example output**

For *"customer support agent for small e-commerce shops"*, `IDEA.md` might conclude:

| Section | Example answer |
| --- | --- |
| User | Support agent at a shop with 10–50 orders/day |
| Problem | Tickets and order details live in different places |
| Product | Inbox where each ticket shows linked order context |
| v1 | Login, ticket list, ticket detail + fake order, mark resolved |
| Will someone pay? | Unknown — needs conversations with shop owners |
| Decision | **pursue** to validate with a demo and 5 outreach calls |

**Result**

A local `IDEA.md` and a **pursue**, **pivot**, or **kill** recommendation in chat.

**Next**

Step 2.

---

## Step 2 — Review and decide

**Do**

1. Read `IDEA.md`.
2. Confirm or override the recommendation.

| Decision | What to do |
| --- | --- |
| **kill** | Stop. Do not continue to [new-project.md](new-project.md). |
| **pivot** | Edit the idea or re-run the **idea** skill with a narrower scope. |
| **pursue** | Go to Step 3. |

**Result**

A clear yes or no on whether this idea becomes a project.

**Next**

Step 3 only if **pursue**.

---

## Step 3 — Turn the idea into a project

**Do**

1. Open [new-project.md](new-project.md).
2. Copy answers from `IDEA.md` into [`templates/PROJECT.md`](../templates/PROJECT.md):
   - **Problem** ← Problem
   - **Users** ← Users
   - **v1 scope** ← Smallest useful version
   - **Out of scope** ← everything not in v1
   - **Done when** ← observable checks from How it works
3. Leave **Constraints** empty unless you already chose stack, auth, or hosting.

**Result**

A `PROJECT.md` ready for the rest of the new-project guide (repo → AGENTS.md → design? → build).

**Next**

[new-project.md](new-project.md) Step 2.

---

## Quick reference

```text
Rough idea
 → idea skill → IDEA.md
 → review → pursue / pivot / kill
 → if pursue → PROJECT.md → new-project.md
```

For what clarity you have at each stage after this, see [from-scratch.md](from-scratch.md).

Full worked example (support agent, all 11 steps): [workflows.md](workflows.md#own-product-from-vague-idea-full-walkthrough).
