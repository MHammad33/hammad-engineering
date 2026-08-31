# Debugging

Step-by-step guide when something is broken. Find the cause before rewriting code.

## Before you start

You have an existing project. Something fails: a button, an API, a production error, or unexpected behavior.

Open this guide from the [README](../README.md) **Start here** section.

---

## Step 1 — Capture the problem

**Do**

1. Write down what you see (error text, screenshot, steps).
2. Note when it started and who is affected if you know.
3. Gather logs or stack traces if available.

**Result**

A clear symptom list the agent can use.

**Next**

Step 2.

---

## Step 2 — Run debug

**Do**

1. Run the **debug** skill with symptoms and reproduction steps.
2. Let the agent reproduce or explain why it cannot.
3. Wait for a root cause and a proposed minimal fix.

**Example prompt**

```text
Use the debug skill. The "Add task" button does nothing when clicked.
```

**Production example**

```text
Use the debug skill. Users get 500 errors when uploading videos. Here are the logs: ...
```

**Result**

A debug report: symptoms, root cause, proposed fix, risk.

**Next**

Step 3. Do **not** start a large rewrite yet.

---

## Step 3 — Approve the fix

**Do**

1. Read the proposed fix.
2. Reply **approved**, or ask for a different approach.

**Skip when**

You already asked the agent to fix it and the cause and fix are both obvious and small. Still prefer a short confirmation for production issues.

**Result**

Agreement on the smallest safe fix.

**Next**

Step 4.

---

## Step 4 — Build the fix

**Do**

1. Run **build** for the approved fix only.
2. Do not mix in refactors or unrelated cleanup.

**Result**

A focused code change.

**Next**

Step 5.

---

## Step 5 — Test

**Do**

1. Run the **test** skill.
2. Confirm the original symptom is gone.
3. Check nearby failure paths if relevant.

**Result**

Evidence the fix works, or a clear failure to address.

**Next**

If tests fail → return to **debug** or **build**. If they pass → done, or Step 6 if the fix was large or risky.

---

## Step 6 — Review (when needed)

**Do**

1. Run **review** for production fixes, security-sensitive changes, or large patches.
2. Address findings before merge.

**Skip when**

The fix is a tiny, obvious one-liner and tests passed.

**Next**

Done. Use [Start here](../README.md#start-here) for the next situation.

---

## Small bug vs production

| Situation | Path |
| --- | --- |
| Local / clear bug | debug → build → test |
| Production / unknown cause | debug → **approve** → build → test → review (if risky) |

## Quick reference

```text
capture symptoms
 → debug
 → approve fix (especially production)
 → build
 → test
 → review (if needed)
```

## Principles

- Root cause before rewrite.
- Smallest fix that addresses the cause.
- Prefer evidence over guessing.
- Do not use **design** or **plan** unless the fix becomes a real project.

Skill lookup if you get stuck: [choosing-a-skill.md](choosing-a-skill.md).
