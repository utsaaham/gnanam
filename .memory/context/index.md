# Context

This folder is the project's memory of itself — what it is, how it works, and what is happening.

## Before You Create Anything

1. Read the codebase first
2. Look at every folder and file in the root — what does each one do?
3. If there is a README, what does it say?
4. If there is an app folder, what is in it?
5. If there is an API, what does it do?
6. If there are config files, what do they set up?
7. Based on what you find, document the project

## What to Create

Once you understand the project, create files like:

- **project-brief.md** — What this project is in plain words. What it does, who it is for, what problem it solves.
- **tech-context.md** — What technologies are used, how to set up the project, how to run it.
- **active-context.md** — What is being worked on right now, what changed recently, what is next.
- **progress.md** — What is done, what is in progress, what is left to build.
- **decisions.md** — Important technical decisions and why they were made.

Each file should describe what is actually in the codebase. For example:
- "In the `app/` folder, we have the main application with these routes..."
- "In `core.py`, we have the business logic that handles..."
- "The `api/` folder contains endpoints for..."

## Rules

- Only document what actually exists
- Use simple language — a non-coder should understand what the project does
- Keep files concise — every line costs context window space
- Update files when things change
- Update this file with a list of context files once they are created
