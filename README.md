# hammad-engineering

Your personal AI engineering workflow. Tool-neutral. Use it to know **what to do next** when working with coding agents.

## What is this?

A small set of skills and guides that turn recurring decisions into a clear path:

```text
IDEA
 ↓
UNDERSTAND
 ↓
DESIGN
 ↓
PLAN
 ↓
BUILD
 ↓
TEST
 ↓
REVIEW
 ↓
DONE
```

Not every task uses every step. Small bugs skip design. Trivial fixes skip review. The agent should match process to the work.

## Why do I have it?

To remove decision fatigue. Instead of guessing what to ask the agent next, open this repo, pick a starting skill, and follow the handoff.

## What should I do first?

| Situation | Start here |
| --- | --- |
| **New project from an idea** | [docs/new-project.md](docs/new-project.md) |
| **New machine or reinstall skills** | [docs/install.md](docs/install.md) |
| **Working on an existing project** | [I have X — start here](#i-have-x--start-here) below |
| **Want a full worked example** | [docs/workflows.md](docs/workflows.md) |

## Install skills

```bash
npx skills add MHammad33/hammad-engineering
```

Details, verify steps, and tool setup: [docs/install.md](docs/install.md).

---

## I have X — start here

| Situation | Start skill | Typical path |
| --- | --- | --- |
| I have a new idea | — | [new-project.md](docs/new-project.md) |
| I need to explore code first | `understand` | understand → design or build |
| I need to design a feature | `design` | design → **approve** → plan or build |
| Design is approved | `plan` or `build` | plan → build → test **or** build → test |
| I know what to build | `build` | build → test |
| Something is broken | `debug` | debug → build → test |
| Production is failing | `debug` | debug → **approve fix** → build → test |
| I changed code | `test` | test → review (if non-trivial) |
| I want another pair of eyes | `review` | review → build (if fixes needed) |
| Code works but feels messy | `improve` | improve → test |

**Invoke a skill by name:**

```text
Use the debug skill. The add button does nothing when clicked.
```

---

## After each step

| You just finished | Do this next |
| --- | --- |
| `understand` | **design** (choices exist) or **build** / **debug** (clear path) |
| `design` | **Wait for your approval**, then **plan** or **build** |
| `plan` | **build** task 1 → **test** |
| `build` | **test** |
| `test` (all pass, non-trivial) | **review** |
| `debug` | **Approve fix**, then **build** → **test** |
| `improve` | **test** |
| `review` (fix required) | **build** → **test** → **review** again if needed |

---

## When to skip a step

| Step | Skip when |
| --- | --- |
| understand | Exact change is obvious |
| design | Constraints and scope are already in `PROJECT.md` or chat |
| plan | Single-step work |
| review | Trivial one-line fix |
| debug | Cause and fix are obvious |

---

## How to use this in a real project

1. **New project:** follow [docs/new-project.md](docs/new-project.md). Copy [templates/PROJECT.md](templates/PROJECT.md) before creating the repo. Copy [templates/project-AGENTS.md](templates/project-AGENTS.md) after.
2. **Existing project:** open this README, pick a skill, run it in the project repo.
3. **Project artifacts stay in the project:** `PROJECT.md`, `AGENTS.md`, `docs/<feature>/design.md`.
4. **This repo stays portable:** principles here, project facts in each project.

---

## Typical workflow examples

**Small bug**

```text
debug → build → test
```

**New feature**

```text
understand → design → approve → plan → build → test → review
```

**Messy working code**

```text
understand → improve → test
```

More examples: [docs/workflows.md](docs/workflows.md).

---

## Skills

| Skill | Purpose |
| --- | --- |
| [understand](skills/understand/SKILL.md) | Learn relevant code before changing it |
| [design](skills/design/SKILL.md) | Decide what to build; wait for approval |
| [plan](skills/plan/SKILL.md) | Split approved work into ordered tasks |
| [build](skills/build/SKILL.md) | Implement the smallest complete change |
| [test](skills/test/SKILL.md) | Verify with evidence |
| [review](skills/review/SKILL.md) | Independent read-only review (subagent) |
| [debug](skills/debug/SKILL.md) | Find root cause before fixing |
| [improve](skills/improve/SKILL.md) | Simplify without changing behavior |

Agent policy for all projects: [AGENTS.md](AGENTS.md).

---

## Templates

| Template | Use |
| --- | --- |
| [templates/PROJECT.md](templates/PROJECT.md) | Project brief before or at repo creation |
| [templates/project-AGENTS.md](templates/project-AGENTS.md) | Agent instructions per project |
