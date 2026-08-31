<div align="center">

<img src="assets/hero.svg" alt="Idea to done: understand, design, plan, build, test, review" width="800">

# Compass

**Understand. Design. Build. Verify.**

[Why](#why) · [Install](#install) · [Choose a skill](#choose-a-skill) · [Guides](#guides)

A small set of skills for coding agents. Use it when you do not know what to do next.

</div>

## Why

Agents need a clear outcome, the constraints that matter, and proof that the work is done. Compass turns that into eight focused skills.

## Install

```bash
npx skills add MHammad33/hammad-engineering
```

Setup and troubleshooting: [docs/install.md](docs/install.md)

## Choose a skill

| You need to… | Start with |
| --- | --- |
| Start a new project | [New project](docs/new-project.md) |
| Decide how a change should work | `design` |
| Fix something that is broken | `debug` |
| Implement a decided task | `build` |

Small work can skip steps. Full lookup: [docs/choosing-a-skill.md](docs/choosing-a-skill.md)

## Skills

| Group | Skills |
| --- | --- |
| Learn | `understand` |
| Decide | `design` · `plan` |
| Deliver | `build` |
| Check | `test` · `review` · `debug` · `improve` |

Instructions live in [`skills/`](skills/). Agent policy lives in [`AGENTS.md`](AGENTS.md).

## Guides

| Guide | Open when |
| --- | --- |
| [Choosing a skill](docs/choosing-a-skill.md) | You need the next skill |
| [New project](docs/new-project.md) | You have an idea and no repo |
| [Workflows](docs/workflows.md) | You want a worked example |
| [Install](docs/install.md) | Skills are missing or outdated |

New repos copy [templates/PROJECT.md](templates/PROJECT.md) then [templates/project-AGENTS.md](templates/project-AGENTS.md).

## Project

Compass is a workflow, not an issue tracker, agent runtime, or stack cookbook. It is tool-neutral. Keep project facts in each project's `PROJECT.md` and `AGENTS.md`.
