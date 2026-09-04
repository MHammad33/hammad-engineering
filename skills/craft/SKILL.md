---
name: craft
description: "Create a new skill, or restructure an existing one, in skills/. Use when adding, renaming, splitting, or restructuring a skill. Not for a small wording edit, and not for a full before/after test with real subagent runs — hand that to the skill-creator plugin."
argument-hint: "<new skill name/purpose, or existing skill to edit>"
---

# Craft

Write or restructure a skill so it holds up on its own and still fits the other nine.

## When to use

- Adding a new skill
- Restructuring, renaming, or splitting an existing one
- Not sure if a skill change needs updates elsewhere in the repo (README, AGENTS.md, docs, templates)

## When not to use

- A wording tweak that doesn't touch structure — just edit the file
- You want a real before/after comparison, run through subagents and graded — that's the `skill-creator` plugin's job

## What actually gets a skill picked

Only the frontmatter `description` (and `when_to_use`, if set) loads into context at the start of a session. The body — including a `## When to use` section — doesn't load until the skill is already invoked. So the body's `When to use` section helps a human skim the file, or helps Claude double-check itself once the skill is open. It does nothing for whether Claude picks the skill in the first place. If a skill isn't triggering when it should, the fix is almost always the `description`, not the body.

## Principles

- **Be concise.** A skill's content, once loaded, stays in the conversation and survives compaction — but only up to 5,000 tokens per skill, shared across a 25,000-token budget for every skill used that session. A long skill isn't just harder to read. It's the first one dropped when a session runs long.
- **Point to shared rules, don't restate them.** Sentence-level tone and style — short sentences, plain words, no filler, name the actor — lives once, in `AGENTS.md`'s Writing section. A skill's own prose should only say what's specific to that skill: its process, its output shape, its boundaries. If you find yourself writing a "Writing rules" section inside a skill, that content almost certainly belongs in `AGENTS.md` instead.
- **Replace a vague claim with a checkable one.** Not "important" or "significant" — a number, a named scale, or an observable rule. The difference between `[severity] description` and a defined scale (say, three named priority levels plus a 0–5 confidence rating, each with a one-line meaning) is the difference between a vibe and something a reader can apply the same way twice.
- **Match freedom to risk.** Loose, prose-style guidance when several approaches would work. An exact command, with no room to improvise, only when a wrong step is costly or hard to undo.
- **Put the real trigger in the frontmatter.** State what the skill does and when, in third person, with the single most important case first — the listing truncates long descriptions, so don't bury the point. If `description` alone won't fit both what and when cleanly, use `when_to_use` for the rest.
- **Know the other frontmatter levers, and use them on purpose:**
  - `disable-model-invocation: true` — only a person can run it, Claude can't auto-trigger it. Worth it for a skill with real side effects or one that should only start on purpose.
  - `context: fork` (with `agent: ...`) — runs the skill in its own subagent automatically. Use this instead of writing "spawn a subagent" in prose and hoping it's followed.
  - `allowed-tools` — pre-approves specific commands for the skill's turn, so a known-safe command (like running the project's test suite) doesn't prompt every time.
  - Don't set a field to its own default. `user-invocable: true` is already the default — writing it says nothing.
- **Split what's only sometimes needed, keep what's always needed.** 500 lines is the ceiling for the main file. Move optional detail into a `references/` file, one link away from `SKILL.md` — never a link to a link — and give it a table of contents if it runs past 100 lines.
- **For a long or fragile sequence, give a checklist the agent can copy and check off** (`- [ ] Step 1: ...`). None of the current nine skills do this. Worth adding to anything with more than five real steps — `idea` is the obvious candidate, since it runs over several turns.
- **If output quality depends on a check, name it and say the loop out loud.** A programmatic check: do the thing, validate it, fix what's wrong, repeat, don't move on until it passes. A prose check: name the actual re-read pass — "can a human get the point in one read," "can a fresh agent execute this without asking a product question" — not just "reread before finishing."
- **Skip anything time-sensitive.** No fact that will quietly go stale.
- **Write two or three real test prompts before calling a skill finished.** You don't have to run a full eval. The cheap first check: turn the skill off with `skillOverrides` in settings, run the same prompt with it on and off, and compare. That alone often shows whether the skill is solving a real problem.

## This repo's shape

Anthropic's docs require almost nothing: a name, a description, a body that gets to the point. No `When to use`, no `Stop when`, no `Next` — those aren't official, they're this repo's own invention. They exist because these nine skills aren't standalone. They hand off to each other by name, a human approves at set points (see `AGENTS.md`), and no two should cover the same ground. That's a real constraint most skills don't have.

| Section | Why it's here | Essential? |
| --- | --- | --- |
| When to use / not to use | Not to use names the sibling to use instead, so two skills never claim the same job | Not to use — yes. When to use — closer to a nice-to-have; the description already carries the real trigger |
| Steps | Standard workflow guidance | Yes |
| Output | Only earns its place when the output has a real shape — a report template, a file | No — skip when there's nothing structured to show |
| Stop when | The pipeline needs an explicit "done, don't keep going," or an agent can wander into the next skill's job | Yes — the one thing a chained system can't skip |
| Human approval | Ties to `AGENTS.md`'s approval gates; also worth asking here whether the skill should set `disable-model-invocation` instead of relying on a human to remember to check | Yes, as long as `AGENTS.md` still works this way |
| Next | The literal handoff — where this skill sends you | Yes — no table, no pipeline |

Use the table's rows, in that order, as your section skeleton — `When to use` through `Next`, `Output` only if there's a real shape to show. Depart from it when a skill genuinely needs to — `design`'s document-sections block, `plan`'s dependency-ordering rules. If you depart, say why in your summary instead of quietly dropping a section.

## Steps

1. Read the target skill (if editing) and one sibling of similar size, so you're calibrated. Writing new, skim two or three siblings first. Read `AGENTS.md`'s Writing section too — that's where sentence-level tone rules live, so the skill body doesn't need to restate them.
2. New skill or edit? New: check the name against reserved words, and check its `When to use`/`When not to use` against every sibling — two skills should never plausibly claim the same task. Edit: be clear on what's changing and why, and don't fold in unrelated cleanup.
3. Pick the frontmatter deliberately — description and, if needed, `when_to_use`, plus whether `disable-model-invocation`, `context: fork`, or `allowed-tools` apply. Don't just copy the block from a sibling unchanged.
4. Draft or edit the body using This repo's shape.
5. Write two or three test prompts. If you can, run the cheap check — toggle the skill off via `skillOverrides`, run one prompt with it on and off, compare.
6. Run the Consistency checklist.
7. Run the Registration checklist. Apply what you can yourself; note what you're deliberately skipping and why.
8. Report what changed, then stop.

## Consistency checklist

- [ ] `description` (and `when_to_use` if used): third person, key use case first, names concrete triggers
- [ ] Name: one lowercase word, not a reserved word, doesn't overlap a sibling's job
- [ ] No frontmatter field set to its own default
- [ ] `disable-model-invocation`, `context: fork`, and `allowed-tools` were each considered, not just skipped by default
- [ ] Body under 500 lines; `references/` used correctly if it isn't
- [ ] No generic tone/style rule restated here that already lives in `AGENTS.md`'s Writing section
- [ ] Vague or unquantified claims replaced with a concrete rule, scale, or example where one exists
- [ ] Each step's looseness matches how risky or reversible it actually is
- [ ] No fact stated in two places — link to it instead
- [ ] Examples, if any, are concrete input/output pairs, not abstract description
- [ ] No time-sensitive claims; the same word used for the same thing throughout
- [ ] `Stop when` says what does *not* happen here, not just "done"
- [ ] `Next` is a table: situation → next skill

## Registration checklist

A skill's name shows up in more than one file. Adding, renaming, or removing one, check each row:

| File | Update when |
| --- | --- |
| `README.md` — Skills table | Always, for a new/renamed/removed skill |
| `AGENTS.md` — Proportionality table, "When to stop" list | Only if the skill is part of the product workflow (Learn/Decide/Deliver/Check) — not for repo-maintenance skills like this one |
| `docs/choosing-a-skill.md` | Only if it's something a project user would pick by situation |
| `docs/workflows.md` | Optional — add a worked example if it clarifies a non-obvious handoff |
| `templates/` | Only if the skill produces a reusable project artifact (like `IDEA.md`) |

## Output

- The new or edited `skills/<name>/SKILL.md`
- Two or three test prompts, and a note on whether the `skillOverrides` on/off check was run
- A short report: which registration rows you updated, which you skipped and why

## Stop when

The skill matches its shape (or explains why it doesn't), the registration checklist is resolved or explicitly deferred, and the report is delivered. Craft doesn't run the skill it just wrote, and doesn't touch a project's own code, `PROJECT.md`, or `AGENTS.md`.

## Human approval

**Required** before editing a shared file — `README.md`, `AGENTS.md`. Show the diff and confirm. Not required for iterating on a skill's own wording within one response.

## Next

| Situation | Next |
| --- | --- |
| New skill written, want a first real signal | Toggle it off/on with `skillOverrides`, run the same prompt both ways |
| Want a full before/after with subagent runs and grading | `skill-creator` plugin — `/plugin install skill-creator@claude-plugins-official`, then `/reload-plugins` |
| Skill edited, ready to use | Invoke it: "Use the `<name>` skill" |
| Registration updates deferred | Human applies them, or asks **craft** to finish them |
