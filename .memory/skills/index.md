---
state: template
created: 2026-03-26
last_updated: 2026-03-26
last_read: —
updated_by: claude-opus
staleness_days: 10
---

# Skills

This folder holds knowledge about the technologies used in this project.

## Meta-skills (always present)

- **`agent-naming.md`** — How to name agents when creating them under `.memory/agents/`. Read this before touching `agents/`.

## Setup Instructions

1. Read the codebase first
2. Identify: languages (Python, JavaScript, TypeScript, Go, etc.)
3. Identify: frameworks (React, FastAPI, Express, Django, etc.)
4. Identify: tools (Docker, databases, CI/CD, etc.)
5. Create one skill file for each technology you find
6. Return here and **replace this entire file** with the populated format

## How to Create a Skill File

Each skill file describes how a technology is used in THIS project — not general knowledge.

```
skills/
  python.md       — Only if Python is used
  react.md        — Only if React is used
  database.md     — Only if a database is used
  docker.md       — Only if Docker is used
```

A skill file should cover:
- What version or setup is used in this project
- Patterns and conventions followed here
- Common operations and how they are done
- Things to watch out for

## Rules

- Only create skill files for technologies that exist in the codebase
- Write about how things are done HERE, not how they are done in general
- Keep it practical — patterns, examples, gotchas

---

## Populated Format

> When you populate this file, delete everything above and use this format instead:

```markdown
# Skills

## Technology Stack

| Skill | Version | Skill File | Used By |
|-------|---------|-----------|---------|
| [Language] | [version] | `skills/[name].md` | [Agent Name] |
| [Framework] | [version] | `skills/[name].md` | [Agent Name] |

## Actions

- **New technology added to the project?** Create a skill file and link it to the relevant agent.
- **Version changed?** Update the version in this table and the skill file.
```
