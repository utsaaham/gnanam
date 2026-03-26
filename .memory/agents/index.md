# Agents

This folder holds the team — the AI personas that handle different parts of the project.

## Before You Create Anything

1. Read the entire codebase first
2. Understand what languages, frameworks, and areas the project has
3. Based on what you find, create agents that match what the project actually needs

## How to Create an Agent

Each agent gets its own folder with two files:

```
agents/
  agent-name/
    persona.md    — Who they are, how they think, what they focus on
    skills.md     — What technologies they know, what tools they use
```

## Examples

- If the project uses Python and has a backend API, create a backend agent with Python and API skills
- If the project has a React frontend, create a frontend agent with React and UI skills
- If the project uses Docker and has deployment configs, create a DevOps agent
- If the project is simple and uses only one language, you might only need one agent

## Rules

- Only create agents for what the project actually has
- Don't create agents for technologies the project doesn't use
- Each agent should have a clear, non-overlapping responsibility
- Update this file with a table of agents once they are created
