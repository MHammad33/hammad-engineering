---
name: improve
description: "Simplify existing code without changing intended behavior. Use when code works but is hard to maintain."
user-invocable: true
argument-hint: "<files, module, or area to improve>"
---

# Improve

Make code clearer and easier to maintain without changing intended behavior.

## When to use

- Code works but is hard to read or change
- User asks for refactor or cleanup without behavior change
- After a feature ships and you want safe local simplification

## When not to use

- Bug fix needed (use **debug** then **build**)
- New feature (use **design** and **build**)
- Large rewrite that changes behavior or interfaces
- No tests or verification path for behavior preservation

## Steps

1. Read the target code and **understand** current behavior.
2. State what will not change (public behavior, interfaces, outputs).
3. Refactor in small steps. Prefer local clarity over large moves.
4. Do not mix behavior changes with cleanup.
5. Run tests or other checks to prove behavior is preserved.
6. Hand off to **test** for a full report.

## Output

- Refactored code
- Summary of what improved (names, structure, duplication removed)
- Evidence that behavior is preserved

## Stop when

The scoped improvement is done and preservation evidence is reported.

## Human approval

Required if refactor scope grows beyond the stated target or touches public interfaces.

Ask before expanding scope.

## Next

**test** — confirm behavior preservation and report evidence.

If behavior must change, stop **improve** and switch to **design** and **build**.
