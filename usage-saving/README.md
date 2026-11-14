# Usage-saving pack

> Legacy snapshot: these paths and commands remain available for compatibility. For the current standalone repositories and new installations, see the [repository index](../README.md).

Seven small skills and one weekly workflow that help AI assistants and agents use less (fewer calls, less context, fewer scheduled wake-ups) without losing quality or anything important.

The skills live next to the other skills in this repository, in [`../skills/`](../skills/).

| Skill | Use it when |
|---|---|
| [`usage-saving`](../skills/usage-saving/SKILL.md) | Planning any task, pipeline or scheduled job; reviewing a setup for cost. Start here. |
| [`lean-chats`](../skills/lean-chats/SKILL.md) | A chat is long, a project wraps, or work moves to a new chat. Includes a handover note template. |
| [`clean-and-compact`](../skills/clean-and-compact/SKILL.md) | One assistant's chat, memory or files have built up. Compacts, refreshes memory, archives files. |
| [`frugal-routines`](../skills/frugal-routines/SKILL.md) | Creating or reviewing scheduled jobs, digests, monitors and watches. |
| [`cheap-delegation`](../skills/cheap-delegation/SKILL.md) | Spawning subagents, picking effort levels, writing briefs. Includes a brief template. |
| [`reuse-before-research`](../skills/reuse-before-research/SKILL.md) | Before researching, and after research worth keeping. |
| [`weekly-cleanup-review`](../skills/weekly-cleanup-review/SKILL.md) | The weekly workflow: backs up skills, cleans idle assistants, proposes up to three cuts. |

[WORKFLOW.md](WORKFLOW.md) shows how they fit together.

## The weekly loop

```
Monday morning (one routine for the whole setup)
  │
  ├─ 1. Back up skills + workflows ........ dated archive folder
  ├─ 2. Read the usage report ............. most-used assistants first
  ├─ 3. For each assistant:
  │       mid-project? ──► skip, list "in progress"
  │       long + idle? ──► clean-and-compact (handover, memory, archive files)
  │       tidy?        ──► leave alone
  ├─ 4. Flag duplicate skills and routines  propose merges, never delete
  ├─ 5. Propose at most 3 usage cuts ...... biggest first, with trade-offs
  └─ 6. One short report ──► owner approves what to apply
```

## Principles
- Compact into a handover note before starting a chat fresh; never restart mid-project.
- Never interrupt in-flight work. Clean it next time.
- Archive, don't delete. Deletion needs the owner's yes.
- Routines on weekdays and waking hours, event triggers over polling, merge duplicates, stay quiet when nothing changed.
- Reuse skills and earlier notes before researching again. Read old transcripts sparingly.
- Delegate big, independent work to background workers with tight briefs; do small lookups yourself.
- Never cut correctness, reviews, approvals or safety checks to save usage.

## Install

Each skill is a folder with a `SKILL.md` (YAML frontmatter with `name` and `description`, then instructions), following the open [Agent Skills format](https://agentskills.io/specification). Plain Markdown: no scripts, no network access, no dependencies.

**Any agent that supports the skills CLI** (Claude Code, Cursor, Codex and others):

```bash
npx skills add felipepetersmann22-star/agent-skills                           # everything in the repo
npx skills add felipepetersmann22-star/agent-skills --skill clean-and-compact # just one
```

**Cursor**: copy the folders from `skills/` into `.cursor/skills/` in a project, or `~/.cursor/skills/` for all projects.

**Claude Code**: copy them into `.claude/skills/` or `~/.claude/skills/`.

**Assistants that save skills from chat** (for example Grok Bot): paste the contents of a `SKILL.md` into a chat and ask the assistant to save it as a skill. One skill per message; keep the name as written. Then ask it to set up `weekly-cleanup-review` as a weekly routine.

Install the whole set if you can. The skills point to each other by name; each still works alone.

## Notes
- If your platform has built-in skills for routines, usage reports or saving skills, keep them. These skills defer to them for mechanics and real usage figures.
- Test a skill on a few of your own tasks before relying on it.

## License
MIT for the files in this pack (the seven skills listed above and this folder). See [LICENSE](LICENSE). Credits in [CREDITS.md](CREDITS.md).
