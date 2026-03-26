---
state: template
created: 2026-03-26
last_updated: 2026-03-26
last_read: —
updated_by: claude-opus
staleness_days: 7
---

# Agents

No agents have been created yet.

## Setup Instructions

You need to read the codebase before creating agents. Do the following:

1. Scan the project root and all subdirectories
2. Identify: languages, frameworks, infrastructure tools, test frameworks
3. For each distinct technology domain, create an agent folder under `agents/`
4. Each agent folder contains `persona.md` and `skills.md`
5. Return here and **replace this entire file** with the populated format below

## Agent Folder Structure

```
agents/
  {agent-name}/
    persona.md    — Identity, focus area, thinking style
    skills.md     — Technologies, tools, patterns they own
```

## Examples

- If the project uses Python and has a backend API → create a `python-backend` agent
- If the project has a React frontend → create a `react-frontend` agent
- If the project uses Docker and has deployment configs → create a `devops` agent
- If the project is simple and uses only one language → you might only need one agent

## Rules

- Only create agents for what the project actually has
- Don't create agents for technologies the project doesn't use
- Each agent should have a clear, non-overlapping responsibility

---

## Populated Format

> When you populate this file, delete everything above and use this format instead:

```markdown
# Agents

## Team Roster

| Agent | Domain | Technologies | Folder |
|-------|--------|-------------|--------|
| [Name] Agent | [area of ownership] | [tech list] | `agents/[name]/` |

## What Each Agent Owns

### [Name] Agent
- [files/folders they own]
- [responsibilities]

## Actions

- **Add an agent?** Read the codebase for uncovered areas, then create a new folder under `agents/`.
- **Re-analyze the project?** The project may have grown. Re-scan and check if existing agents still cover everything.
```
