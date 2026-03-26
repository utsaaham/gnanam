# Rules

This folder holds the coding rules that every agent must follow. These are laws, not suggestions.

## Before You Create Anything

1. Read the codebase first
2. Look at how the code is written — naming, formatting, structure
3. Look at what patterns are used — how things talk to each other, how errors are handled
4. Look at what tests exist and how they are written
5. Look at how security is handled — auth, secrets, input validation
6. Based on what you find, create rule files that capture the real conventions

## What Kind of Rules to Create

Once you understand the project, consider creating files like:

- **code-style.md** — How code is named, formatted, and organized
- **architecture.md** — What talks to what, what the boundaries are
- **testing.md** — How to test, what to test, what coverage is expected
- **security.md** — How auth works, how secrets are handled, validation rules
- **forbidden.md** — Things you must NEVER do in this project

## Rules

- Only create rules that reflect what the project actually does
- Don't invent rules for a project you haven't read
- Every rule should have a reason behind it
- Update this file with a list of rules once they are created
