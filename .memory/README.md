---
state: template
created: 2026-04-15
last_updated: 2026-04-15
last_read: —
staleness_days: 14
---

# .memory — Shared Project Memory

This is a tool-agnostic memory system. Any AI coding assistant (Claude Code, Codex, Cursor, Windsurf, Gemini CLI, Copilot, Cline, Aider, Zed, Continue) can load it by following the read order below. The root `README.md` has the full tool → instruction file mapping.

## What lives here

| Folder | What it holds |
|--------|---------------|
| `context/` | What the project is, what files exist, what each part does |
| `agents/` | Named team members (human first names) with role personas and skills |
| `skills/` | How this project uses each technology |
| `rules/` | Coding conventions everyone follows — laws, not suggestions |
| `commands/` | Step-by-step recipes for common workflows (deploy, debug, ship) |
| `manager/` | Routing logic — who handles what and how work flows |

## Read order

### First-time setup (memory is empty)
If `project-memory.md`'s Memory Status table shows "Not yet created" for every section:

1. Read the entire codebase — every folder, every file.
2. Open each `index.md` under `.memory/` — each explains what to create.
3. Populate in this order: `context/` → `agents/` → `skills/` → `rules/` → `commands/`.
4. Update the Memory Status table in `project-memory.md` with today's date.
5. Flip each `index.md` frontmatter from `state: template` to `state: populated`.

### Returning (memory already populated)
1. Open `project-memory.md` and check the Memory Status table.
2. For any section past its "Stale After" threshold, re-read the relevant codebase area and update that section.
3. Set `last_read` in `project-memory.md` frontmatter to today's date.
4. Load only the sections you need for your task:
   - Writing code? → `rules/index.md`
   - Using a specific tech? → `skills/index.md`
   - Running a workflow? → `commands/index.md`
   - Routing or coordination? → `manager/manager.md`
5. Start the task.

## After significant work

1. Update the touched files under `.memory/`.
2. Update `last_updated` in those files' frontmatter.
3. Update the Memory Status table in `project-memory.md`.
4. Keep files concise — every line costs context window space.

## Agent naming

Agent folders under `agents/` are named after real human first names drawn from any culture (Kevin, Priya, Hiroshi, Aaliyah, Kofi...). The role — devops, frontend, backend, etc. — is described inside each agent's `persona.md`, not in the folder name. See `skills/agent-naming.md` for the full rule and seed name pool.
