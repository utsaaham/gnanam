---
state: template
created: 2026-03-26
last_updated: 2026-03-26
last_read: —
updated_by: claude-opus
staleness_days: 3
---

# Project Memory

> This is the starting point for any AI agent working on this project.
> Every tool — Cursor, Claude Code, Windsurf, Cline, Copilot, Gemini, Codex — starts here.
> Do NOT start working without reading this file.

---

## Memory Status

| Section | Last Updated | Updated By | Stale After | Status |
|---------|-------------|------------|-------------|--------|
| context/ | — | — | 3 days | Not yet created |
| agents/ | — | — | 7 days | Not yet created |
| skills/ | — | — | 10 days | Not yet created |
| rules/ | — | — | 14 days | Not yet created |
| commands/ | — | — | 14 days | Not yet created |

---

## What is in `.memory/`

| Folder | What it holds |
|--------|--------------|
| `context/` | What the project is, what files we have, what each part does |
| `agents/` | Team members who handle different parts of the code |
| `rules/` | The rules everyone follows when writing code |
| `skills/` | Knowledge about the technologies we use |
| `commands/` | Step-by-step guides for common tasks (deploy, fix a bug, etc.) |
| `manager/` | The boss — decides who handles what and how work flows |

---

## First Time Here?

If the Memory Status table above shows "Not yet created" for everything:

1. **Read the entire codebase** — go through every folder and file
2. **Open each `index.md`** in `.memory/` — it tells you what to create based on what you found
3. **Start with `context/`** — document what the project is and what it has
4. **Then `agents/`** — create team members based on what the project needs
5. **Then `skills/`** — document the technologies used
6. **Then `rules/`** — capture the conventions and patterns you see
7. **Then `commands/`** — write step-by-step guides for common workflows
8. **Update the Memory Status table** — put today's date, your name, and "Current" for each section
9. **Change `state` in frontmatter to `populated`** — so returning agents know setup is done

> **Important:** Once populated, replace the "First Time Here?" and "Returning?" sections with a "Quick Start" section. Template instructions should not remain in a populated file.

---

## Returning?

If the Memory Status table has dates in it, the memory has been set up before.

1. **Check the dates and "Stale After" column** — is any section past its staleness threshold?
2. **If stale** — re-read the relevant parts of the codebase and update those sections
3. **Update `last_read` in this file's frontmatter** to today's date
4. **Then start your task** — you now have fresh context

---

## Keeping Memory Updated

After you do significant work:

1. Update the relevant files in `.memory/`
2. Update the **Memory Status table** above with today's date and your name
3. Update `last_updated` in the frontmatter of any file you modified
4. Keep files concise — every line costs context window space
