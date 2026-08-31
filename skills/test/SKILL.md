---
name: test
description: "Verify a change with evidence. Use after build or improve. Reports pass, fail, or unverified for each criterion."
user-invocable: true
argument-hint: "<change description, acceptance criteria, or design path>"
---

# Test

Prove whether the change works. Report evidence, not assumptions.

## When to use

- After **build** or **improve**
- User asks to verify a branch, fix, or feature
- Before **review** or merge when checks are expected

## When not to use

- No code changed (design or plan only)
- User explicitly wants review without running checks yet

## Steps

1. Read the change, acceptance criteria, design test strategy, and project `AGENTS.md` commands.
2. List what must be verified.
3. Run relevant automated tests, lint, and type checks using project commands.
4. Check affected failure paths when they matter.
5. For UI behavior, verify in a real browser when the project has a UI and automated tests do not cover it.
6. Report each criterion as pass, fail, or unverified with reason.

## Output

```markdown
## Test report

### Criteria
- [PASS|FAIL|UNVERIFIED] AC-1: ...
- ...

### Commands run
- `npm test` — result
- ...

### Unverified
- What could not be checked and why
```

## Stop when

Every criterion is pass, fail, or explicitly unverified.

## Human approval

Not required. Report failures clearly and suggest **build** fixes if needed.

## Next

| Situation | Next skill |
| --- | --- |
| Non-trivial or risky change | **review** |
| Failures found | **build** to fix, then **test** again |
| Trivial fix, all pass | Done |
