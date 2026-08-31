# Install skills

Install skills once per machine. They work across all projects.

## Install

```bash
npx skills add MHammad33/hammad-engineering
```

Replace `MHammad33/hammad-engineering` with this repository path if you use a fork or private remote.

## Verify

1. Open a project in your agent tool.
2. Confirm skills appear in the skill list or respond to explicit invocation.
3. Run a test prompt:

```text
Use the understand skill. Summarize what this repository does in one paragraph.
```

If the agent follows the skill structure, installation worked.

## Update

```bash
npx skills update MHammad33/hammad-engineering
```

Run update after pulling changes from this repository.

## Troubleshooting

| Problem | What to do |
| --- | --- |
| Skills do not appear | Re-run install. Restart the agent tool. Check [install](#install) path. |
| Old skill behavior | Run [update](#update). |
| Agent ignores a skill | Invoke it by name: `Use the debug skill. ...` |

---

## Cursor

1. Install skills with the command above.
2. Skills are loaded from the skills directory configured by the `skills` CLI.
3. Invoke by name in chat: `Use the design skill. ...`
4. Keep project-specific rules in the project repo (`AGENTS.md`, `.cursor/rules/` if you use them).
5. Keep Compass workflow rules in this repository, not in Cursor settings, when possible.

## Other tools

Add a section here when you adopt another agent tool. Keep the [install](#install) steps tool-neutral at the top. Put tool-specific wiring in a section below.
