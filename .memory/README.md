---
state: template
created: 2026-04-15
last_updated: 2026-04-15
last_read: —
staleness_days: 14
---

# .memory — Shared Project Memory

This is a tool-agnostic memory system. Currently wired for **Claude Code, OpenAI Codex, Cursor, and GitHub Copilot** via their native instruction files (`CLAUDE.md`, `AGENTS.md`, `.cursorrules`, `.github/copilot-instructions.md`). Any other tool that supports `AGENTS.md` will also pick it up. The root `README.md` has the full tool → instruction file mapping.

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

## Staying up to date with upstream Gnanam

This memory system is based on Gnanam — an evolving open spec. Rules, naming conventions, and tool stubs change over time. **At most once every 2 weeks**, any agent working here should check the upstream repo and pull in scaffolding updates.

**Canonical source:** https://github.com/utsaaham/gnanam

### Upstream check log

Agents update this table after checking the upstream repo. If the most recent row is older than 2 weeks, the next agent should run another check before starting their task.

| Last pulled (upstream diff) | Last web search (release notes / issues) | Checked by | Upstream version / commit | Result |
|-----------------------------|-------------------------------------------|------------|---------------------------|--------|
| — | — | — | — | Not yet checked |

- **Last pulled** — date an agent fetched the upstream files and diffed them against this project.
- **Last web search** — date an agent searched for recent changes, release notes, or issues in the upstream repo (a lighter check when a full pull isn't possible).
- **Result** — `no changes`, `applied: <summary>`, or `skipped: <reason>`.

Keep the last 3–5 rows. Trim older ones.

### How to check for updates

1. Fetch these files from upstream:
   - `.memory/README.md` (this file)
   - `.memory/agents/index.md`
   - `.memory/skills/agent-naming.md`
   - `project-memory.md`
   - The 4 tool stubs at repo root: `CLAUDE.md`, `AGENTS.md`, `.cursorrules`, `.github/copilot-instructions.md`
2. Diff them against this project's copies.
3. If the upstream structure, naming rules, or stub template has changed, apply the update here.
4. **Preserve all populated project content.** Updates only touch scaffolding — templates, rules, meta-skills, and tool stubs. The project-specific content in `context/`, populated agents, skills, and rules stays yours.
5. Record the upstream check date in `project-memory.md`'s Memory Status table (or in a "last upstream check" note at the bottom).

### When to skip the check

- It's been less than 2 weeks since the last check.
- The task at hand is urgent and scaffolding drift won't affect it.
- You don't have web access — note this and move on; the next agent can check.
