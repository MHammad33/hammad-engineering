![Compass. Understand. Design. Build. Verify.](assets/hero.png)

# Compass

**Understand. Design. Build. Verify.**

A small set of skills for coding agents. Use it when you do not know what to do next.

## Why

Agents need a clear outcome, the constraints that matter, and proof that the work is done. Compass turns that into eight focused skills. Use only the steps the work needs.

## Install

```bash
npx skills add MHammad33/hammad-engineering
```

Verify, update, and tool setup are in [docs/install.md](docs/install.md).

## Choose a skill

Most work starts in one of these places:

- **New project** — follow [docs/new-project.md](docs/new-project.md)
- **Meaningful change** — run `design`, then wait for approval
- **Something broken** — run `debug` before changing code

Small, decided work can go straight to `build`.

Full lookup, handoffs, and skip rules: [docs/choosing-a-skill.md](docs/choosing-a-skill.md).

## Skills

| Group | Skills |
| --- | --- |
| Learn | `understand` |
| Decide | `design`, `plan` |
| Deliver | `build` |
| Check | `test`, `review`, `debug`, `improve` |

Each skill is in [`skills/`](skills/). Policy for all projects is in [`AGENTS.md`](AGENTS.md).

## Guides

| Guide | When to open it |
| --- | --- |
| [Choosing a skill](docs/choosing-a-skill.md) | You have a task and need the next skill |
| [New project](docs/new-project.md) | You have an idea and no repo yet |
| [Workflows](docs/workflows.md) | You want a worked example |
| [Install](docs/install.md) | Skills are missing or outdated |

Copy [templates/PROJECT.md](templates/PROJECT.md) and [templates/project-AGENTS.md](templates/project-AGENTS.md) when starting a project.

## Project

Compass lives in this repository. It is not an issue tracker, an agent runtime, or a stack cookbook. It is tool-neutral. Keep project facts in each project's `PROJECT.md` and `AGENTS.md`.
