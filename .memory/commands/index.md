---
state: template
created: 2026-03-26
last_updated: 2026-03-26
last_read: —
updated_by: claude-opus
staleness_days: 14
---

# Commands

This folder holds step-by-step workflows for common tasks in this project.

## Setup Instructions

1. Read the codebase first
2. Understand how development works — how to run, test, and build the project
3. Understand how deployment works — what steps are needed to ship code
4. Understand common tasks — what do people do repeatedly?
5. Based on what you find, create command files as step-by-step recipes
6. Return here and **replace this entire file** with the populated format

## What Kind of Commands to Create

- **new-feature.md** — Steps to add a new feature from start to finish
- **fix-bug.md** — Steps to investigate and fix a bug
- **deploy.md** — Steps to deploy the project
- **refactor.md** — Steps to safely refactor code

## How a Command File Should Look

Each command file is a recipe — clear steps anyone can follow:

1. What to do first
2. What to do next
3. How to verify it worked

## Rules

- Only create commands for workflows that make sense for this project
- Write them so that someone new to the project can follow along
- Keep them practical and specific, not generic

---

## Populated Format

> When you populate this file, delete everything above and use this format instead:

```markdown
# Commands

## Available Workflows

| Command | File | When to Use |
|---------|------|------------|
| [Name] | `commands/[name].md` | [when to use it] |

## Actions

- **Repeated a workflow 3+ times without a command file?** Create one.
- **Workflow changed?** Update the command file.
```
