---
name: debug
description: "Find root cause of broken behavior systematically. Use for errors, bugs, and production issues. Do not rewrite code before the cause is understood."
user-invocable: true
argument-hint: "<symptoms, errors, logs, reproduction steps>"
---

# Debug

Find why something is broken before applying a fix.

## When to use

- Errors, crashes, or unexpected behavior
- Production incidents
- Bug reports with unknown cause
- User says something is broken

## When not to use

- Feature request with no failure
- Behavior-preserving cleanup (use **improve**)
- Cause and fix are already obvious from a quick read

## Steps

1. Capture symptoms: error messages, logs, steps to reproduce, scope of impact.
2. Reproduce the issue or state clearly why reproduction failed.
3. Form a hypothesis. Investigate the smallest relevant code path.
4. Narrow to root cause. Distinguish symptom from cause.
5. Propose the **smallest fix** that addresses the root cause.
6. Do not rewrite unrelated code. Do not start large refactors.

## Output

```markdown
## Debug report

### Symptoms
What the user sees

### Reproduction
Steps and result (or why not reproduced)

### Root cause
What actually breaks and where

### Proposed fix
Minimal change recommended

### Risk
What could go wrong with the fix
```

## Stop when

Root cause is identified and a fix is proposed.

## Human approval

**Required** before large or risky fixes, or when root cause is uncertain.

Ask: "Approve this fix? Reply approved or request a different approach."

For obvious minimal fixes, state the fix and proceed to **build** only if the human already asked you to fix it.

## Next

After approval:

```text
build → test
```

If cause is still unknown, state what evidence is missing and ask the human.
