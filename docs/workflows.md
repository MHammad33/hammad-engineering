# Workflows

Worked examples for common situations. For a quick lookup, use [Choosing a skill](choosing-a-skill.md).

Each example lists: situation, starting skill, path, and what done looks like.

---

## Small bug

**Situation**

A button stopped working in an existing project. The app is otherwise set up.

**Start with**

`debug` (or `understand` if the cause is likely obvious)

**Path**

```text
debug → [approve fix if needed] → build → test
```

**Example prompt**

```text
Use the debug skill. The "Add task" button does nothing when clicked.
```

**Skip**

design, plan, review (unless the fix is large or risky)

**Done when**

The button works and relevant tests pass or are honestly marked unverified.

---

## New feature

**Situation**

You want Google sign-in on an existing app. Real choices exist: OAuth flow, sessions, env vars.

**Start with**

`design`

**Path**

```text
understand (if needed) → design → [wait for approval] → plan (if multi-step) → build → test → review
```

**Example prompt**

```text
Use the design skill. Add Google sign-in. Read PROJECT.md and existing auth code first.
```

**Output**

`docs/google-auth/design.md` in the project repo.

**After approval**

- Multi-step work: `Use the plan skill. Break down the approved design.`
- Simple work: `Use the build skill. Implement the approved design.`

**Done when**

Sign-in works, tests pass, and review findings are addressed or accepted.

---

## Production bug

**Situation**

Users get 500 errors when uploading videos. Cause unknown. Urgent.

**Start with**

`debug`

**Path**

```text
debug → [wait for approval on fix] → build → test
```

**Example prompt**

```text
Use the debug skill. Users get 500 errors on video upload. Here are the logs: ...
```

**Rules**

- Do not rewrite large areas before root cause is known.
- Prefer the smallest fix that addresses the cause.

**Skip**

design, plan (unless the fix becomes a large project)

**Done when**

Upload works, cause is documented, and verification evidence is reported.

---

## Messy but working code

**Situation**

A module works but is hard to maintain. No behavior change requested.

**Start with**

`improve`

**Path**

```text
understand → improve → test
```

**Example prompt**

```text
Use the improve skill. Simplify src/upload-handler without changing behavior.
```

**Skip**

design, plan (unless refactor scope grows)

**Done when**

Code is clearer and tests prove behavior is preserved.

---

## Design approved — what next?

**Situation**

You approved `docs/<feature>/design.md` and need to continue.

**Start with**

`plan` or `build`

**Decision**

| Condition | Next skill |
| --- | --- |
| Several independent steps or multiple sessions | `plan` |
| One clear implementation pass | `build` |

**Example prompts**

```text
Use the plan skill. Break the approved design into ordered tasks.
```

```text
Use the build skill. Implement the approved design in docs/google-auth/design.md.
```

---

## Vague request

**Situation**

You said "add authentication" without naming a skill or scope.

**Agent behavior (AGENTS.md)**

1. State that scope is unclear.
2. Run `understand` on existing code.
3. Recommend `design` if choices exist.
4. Ask before `build`.

**You can override**

Use the README table and invoke a skill directly when you already know the path.

---

## New project (full path)

See [new-project.md](new-project.md) for the complete bootstrap sequence from idea to v1.
