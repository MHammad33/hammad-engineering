---
name: review
description: "Independent read-only review of an implementation. Use a fresh subagent. Reports findings and verdict without editing code."
user-invocable: true
argument-hint: "<branch, PR, diff, or change description>"
---

# Review

Critically evaluate an implementation without changing it.

## When to use

- Non-trivial **build** changes
- Security-sensitive code
- Before merge when you want a second pass
- User asks for a review

## When not to use

- Typo or one-line obvious fix
- No implementation to review yet
- User wants you to fix code (use **build**)

## Steps

1. Read the change scope, design (if any), and project `AGENTS.md`.
2. **Spawn a fresh subagent** for an independent read-only review. Do not reuse the implementation context as the reviewer.
3. Give the subagent: the diff or files, acceptance criteria, and review checklist below.
4. Collect findings: defects, risks, missing proof, unnecessary complexity.
5. Summarize with a verdict. Do not edit the code.

## Review checklist for the subagent

- Correctness: does it meet the stated requirements?
- Regressions: what existing behavior could break?
- Security: auth, input validation, secrets, trust boundaries
- Simplicity: can the same outcome be achieved with less complexity?
- Proof: were tests run? What is still unverified?

## Output

```markdown
## Review

### Findings
- [severity] description

### Verdict
APPROVE | FIX REQUIRED | NEEDS DISCUSSION

### Notes
What the author should do next
```

## Stop when

Findings and verdict are delivered.

## Human approval

The human reads findings and decides what to fix. The reviewer does not implement fixes.

## Next

| Verdict | Next step |
| --- | --- |
| FIX REQUIRED | **build** to address findings, then **test**, then **review** again if needed |
| APPROVE | Done or merge per project process |
| NEEDS DISCUSSION | Human decides before more code |
