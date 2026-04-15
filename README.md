# Gnanam (జ్ఞానం — Knowledge / Awareness)

A portable memory system that lets any AI coding agent onboard itself, remember context across sessions, and coordinate with other agents — without you re-explaining your project every time.

Works with: **Cursor, Claude Code, Windsurf, Cline, Copilot, Gemini, Codex** — any tool that can read markdown.

---

## The Problem

Every time you start a new AI chat, the agent knows nothing about your project. You waste time explaining the same things over and over. If you switch tools, you start from zero again.

## The Solution

Drop `.memory/` and `project-memory.md` into any project. The first AI agent that reads it will:

1. Scan your codebase
2. Document what it finds (languages, frameworks, architecture)
3. Create agent personas matched to your project's needs
4. Capture coding rules and conventions
5. Write step-by-step workflow guides

Every agent after that reads the memory, checks the dates, refreshes anything stale, and gets to work — no hand-holding required.

---

## Quick Start

### Option 1: Add to an existing project

```bash
# Clone gnanam
git clone https://github.com/your-username/gnanam.git

# Copy memory system into your project
cp -r gnanam/.memory your-project/
cp gnanam/project-memory.md your-project/
```

Then open your project in any AI tool and tell it:

> Read `project-memory.md` and follow the first-time setup instructions.

### Option 2: Start a new project here

Add your source code to this repo alongside `.memory/` and `project-memory.md`. Then run the first-time setup with any AI agent.

---

## How It Works

### Entry Point

Every AI agent starts by reading `project-memory.md`. It contains:

- A **Memory Status table** showing what's been documented and when
- A **staleness threshold** per section (context: 3 days, rules: 14 days, etc.)
- Instructions for first-time setup vs. returning agents

### Folder Structure

```
your-project/
├── project-memory.md          ← Start here (entry point for all agents)
├── .memory/
│   ├── context/               ← What the project is and what's happening
│   │   └── index.md
│   ├── agents/                ← AI personas matched to your codebase
│   │   └── index.md
│   ├── skills/                ← Technology-specific knowledge
│   │   └── index.md
│   ├── rules/                 ← Coding conventions and laws
│   │   └── index.md
│   ├── commands/              ← Step-by-step workflow recipes
│   │   └── index.md
│   └── manager/               ← Task routing and workflow coordination
│       ├── manager.md
│       ├── task-router.md
│       └── workflow.md
└── ... your source code ...
```

### Two-State Files

Every index file has two states:

| State | What it looks like | When |
|-------|-------------------|------|
| **Template** | Setup instructions + how to populate | Before first codebase scan |
| **Populated** | Actual project content + "Actions" for next steps | After an agent reads the codebase |

Once populated, all template instructions are removed. The file becomes a clean reference document.

### Date Tracking

Every file has YAML frontmatter:

```yaml
---
state: template        # or "populated"
created: 2026-03-26
last_updated: 2026-03-26
last_read: —
updated_by: claude-opus
staleness_days: 7      # how many days before an agent should re-verify
---
```

- `last_read` — updated every time an agent reads the file
- `last_updated` — updated every time an agent modifies the file
- `staleness_days` — tells returning agents when to refresh (context is volatile at 3 days, rules are stable at 14 days)

### What Each Folder Does

| Folder | Purpose | Staleness |
|--------|---------|-----------|
| `context/` | Project description, tech stack, current work, progress | 3 days |
| `agents/` | Agent personas with domains and technology ownership | 7 days |
| `skills/` | How each technology is used in THIS project | 10 days |
| `rules/` | Coding conventions — laws, not suggestions | 14 days |
| `commands/` | Step-by-step recipes for common tasks | 14 days |
| `manager/` | Task routing, workflow, multi-agent coordination | 7–30 days |

### Multi-Agent Coordination

The manager system enables:

- **Task routing** — incoming tasks get matched to the right agent based on domain
- **Skill loading** — each agent loads only the skills and rules relevant to their task
- **Handoffs** — multi-agent tasks (e.g., full-stack features) follow a defined agent order
- **Verification** — work is checked against rules before it's considered done

### Standard Workflow

Every task follows this flow:

```
RECEIVE → ROUTE → CONTEXT → PLAN → EXECUTE → VERIFY → TEST → UPDATE → DONE
```

No code gets written without loading rules first. No feature ships without tests. Agents state their plan before executing.

---

## Integrating with AI Tools

Each AI tool has its own native instruction file at the repo root. Gnanam ships a ready-made stub for **10 tools** — each file tells the agent to read `project-memory.md` and `.memory/README.md` before doing anything. Pick the one your tool loads automatically; if you use multiple tools, they all point at the same memory so context stays in sync.

| Tool | File | Notes |
|------|------|-------|
| **Claude Code** | `CLAUDE.md` | Loaded automatically by Claude Code. |
| **OpenAI Codex** | `AGENTS.md` | Also the cross-tool open standard (Cursor, Windsurf, Gemini CLI, Zed, RooCode all read it). |
| **Cursor** | `.cursorrules` | Legacy single-file format; still read by Cursor. |
| **Windsurf** | `.windsurfrules` | |
| **Gemini CLI** | `GEMINI.md` | |
| **GitHub Copilot** | `.github/copilot-instructions.md` | |
| **Cline** | `.clinerules` | |
| **Aider** | `CONVENTIONS.md` | Point aider at it via `--read CONVENTIONS.md` or `.aider.conf.yml`. |
| **Zed AI** | `.rules` | |
| **Continue.dev** | `.continuerules` | |

### If you want to add tool-specific rules

Keep the shared stub at the top of the file (so memory still loads), then **append** your tool-specific rules below it. For example, put Claude Code hooks in `CLAUDE.md` under the stub; put Cursor `.mdc` activation modes in `.cursor/rules/` alongside `.cursorrules`. Don't duplicate memory content into the stub — update `.memory/` instead, and every tool picks it up automatically.

### Other tools

If your tool isn't listed above, paste this into your system prompt or first message:

> Read `project-memory.md` and `.memory/README.md` before starting any task.

---

## FAQ

**Does this work with any language or framework?**
Yes. The memory system is language-agnostic. It documents whatever it finds in your codebase.

**What if I switch AI tools mid-project?**
The new tool reads `project-memory.md`, sees the populated memory, and picks up where the last agent left off. That's the whole point.

**How do I reset the memory?**
Change `state: populated` back to `state: template` in any index file, delete the populated content, and re-run the first-time setup.

**Does this add overhead to my repo?**
The `.memory/` folder is all markdown — a few KB at most. Add it to `.gitignore` if you don't want it versioned, but versioning it means your whole team (human and AI) shares context.

---

## Live Example

See Gnanam in action on a real project — fully populated `.memory/` with agents, skills, rules, and context:

- [`.memory/` folder (populated)](https://github.com/utsaaham/arogyamandiram/tree/feature/dev-01/.memory)
- [`project-memory.md` (populated)](https://github.com/utsaaham/arogyamandiram/blob/feature/dev-01/project-memory.md)

This is the [Arogyamandiram](https://github.com/utsaaham/arogyamandiram/tree/feature/dev-01) project — use it as a reference to see what the memory system looks like after an agent has completed the first-time setup.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
