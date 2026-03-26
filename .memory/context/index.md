---
state: template
created: 2026-03-26
last_updated: 2026-03-26
last_read: —
updated_by: claude-opus
staleness_days: 3
---

# Context

This folder is the project's memory of itself — what it is, how it works, and what is happening.

## Setup Instructions

1. Read the codebase first
2. Look at every folder and file in the root — what does each one do?
3. If there is a README, what does it say?
4. If there is an app folder, what is in it?
5. If there is an API, what does it do?
6. If there are config files, what do they set up?
7. Based on what you find, create the context files listed below
8. Return here and **replace this entire file** with the populated format

## What to Create

- **project-brief.md** — What this project is in plain words. What it does, who it is for, what problem it solves.
- **tech-context.md** — What technologies are used, how to set up the project, how to run it.
- **active-context.md** — What is being worked on right now, what changed recently, what is next.
- **progress.md** — What is done, what is in progress, what is left to build.
- **decisions.md** — Important technical decisions and why they were made.

Each file should describe what is actually in the codebase:
- "In the `app/` folder, we have the main application with these routes..."
- "In `core.py`, we have the business logic that handles..."

## Rules

- Only document what actually exists
- Use simple language — a non-coder should understand what the project does
- Keep files concise — every line costs context window space

---

## Populated Format

> When you populate this file, delete everything above and use this format instead:

```markdown
# Context

## Project Summary

[One-line description of the project]. Uses [tech stack]. Main entry point: [file].

## Context Files

| File | What It Covers | Last Updated |
|------|---------------|-------------|
| `context/project-brief.md` | What the project is, who it's for | YYYY-MM-DD |
| `context/tech-context.md` | Tech stack, setup, how to run | YYYY-MM-DD |
| `context/active-context.md` | Current work in progress | YYYY-MM-DD |
| `context/progress.md` | Done / In Progress / To Do | YYYY-MM-DD |

## Actions

- **Starting a new task?** Read `active-context.md` first.
- **Project structure changed?** Update `tech-context.md` and this summary.
- **Finished significant work?** Update `progress.md` and `active-context.md`.
```
