# Improve

Step-by-step guide when code works but is hard to maintain. Change structure, not behavior.

## Before you start

The module or area works correctly. You want clarity, simpler structure, or less duplication — not a new feature and not a bug fix.

Open this guide from the [README](../README.md) **Start here** section.

---

## Step 1 — Understand current behavior

**Do**

1. Run **understand** on the target files or module.
2. State what must stay the same (public behavior, outputs, interfaces).

**Example prompt**

```text
Use the understand skill. Summarize how src/upload-handler works and what callers depend on.
```

**Result**

A clear picture of behavior that must not change.

**Next**

Step 2.

---

## Step 2 — Improve in small steps

**Do**

1. Run the **improve** skill on a scoped target.
2. Prefer local clarity over large moves.
3. Ask before expanding beyond the stated files or touching public interfaces.

**Example prompt**

```text
Use the improve skill. Simplify src/upload-handler without changing behavior.
```

**Result**

Clearer code with the same intended behavior.

**Next**

Step 3.

---

## Step 3 — Test behavior preservation

**Do**

1. Run the **test** skill.
2. Prefer existing tests that cover this area. Add checks only if needed to prove nothing broke.
3. Report pass, fail, or unverified.

**Result**

Evidence that behavior was preserved.

**Next**

If tests fail → fix with **improve** or **build**, then **test** again. If they pass → done, or Step 4 if the refactor was large.

---

## Step 4 — Review (when needed)

**Do**

1. Run **review** for large refactors or shared interfaces.
2. Address findings before merge.

**Skip when**

The change is small and tests give strong coverage.

**Next**

Done. Use [Start here](../README.md#start-here) for the next situation.

---

## Quick reference

```text
understand
 → improve
 → test
 → review (if large)
```

## Principles

- Behavior stays the same. Structure gets clearer.
- Do not mix feature work or bug fixes into **improve**.
- If behavior must change, stop and use [New feature](new-feature.md) or [Debugging](debugging.md).
- Keep the scope small enough to verify.

Skill lookup if you get stuck: [choosing-a-skill.md](choosing-a-skill.md).
