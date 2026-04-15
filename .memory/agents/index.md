---
state: template
created: 2026-03-26
last_updated: 2026-04-15
last_read: —
staleness_days: 7
---

# Agents

No agents have been created yet.

## The naming rule (read this first)

**Every agent folder is named after a real human first name** drawn from any culture worldwide — Kevin, Matthew, Priya, Hiroshi, Aaliyah, Kofi, Fatima, Mateo, and so on. The *role* (devops, nextjs full-stack, backend, QA...) goes inside the folder in `persona.md`, **not** in the folder name.

Full rule + seed name pool: `.memory/skills/agent-naming.md`. Read it before creating any agent.

## Setup instructions

1. Scan the project root and all subdirectories.
2. Identify: languages, frameworks, infrastructure, test tooling.
3. For each distinct domain the project actually needs, pick an unused human first name from the pool in `skills/agent-naming.md`.
4. Create `agents/<firstname>/` with:
   - `persona.md` — `# <Firstname> — <Role>` and what they own.
   - `skills.md` — the technologies, tools, and files that person is responsible for.
5. Return here and **replace this entire file** with the Populated Format below.

## Rules

- Only create agents for domains the project actually has.
- Don't create agents for technologies the project doesn't use.
- Each agent owns a clear, non-overlapping area.
- Never reuse a name that's already in the team.
- Folder names are lowercase ASCII; first names in docs are title case.

---

## Populated Format

> When you populate this file, delete everything above and use this format instead:

```markdown
# Agents

## Team Roster

| Name | Role | Technologies | Folder |
|------|------|-------------|--------|
| Kevin | DevOps | Docker, GitHub Actions | `agents/kevin/` |
| Priya | Backend | Python, FastAPI, Postgres | `agents/priya/` |
| Matthew | Frontend | Next.js, TypeScript, Tailwind | `agents/matthew/` |

## What Each Agent Owns

### Kevin — DevOps
- `Dockerfile`, `docker-compose.yml`, `.github/workflows/`
- Deploy pipeline, environment secrets, release tagging

### Priya — Backend
- `app/api/`, `app/models/`, `app/services/`
- Database migrations, API contracts, background jobs

### Matthew — Frontend
- `web/`, component library, page routing
- Auth flows on the client, UI state management

## Actions

- **Add an agent?** Pick an unused first name from `skills/agent-naming.md`, create the folder, update this roster.
- **Re-analyze the project?** Re-scan the codebase and check whether existing agents still cover everything.
```
