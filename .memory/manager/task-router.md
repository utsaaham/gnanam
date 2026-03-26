# Task Router

The manager reads this file to decide which agent handles a task.

## How Routing Works

1. Read the task
2. Look at the agents table below
3. Match the task to the right agent based on what area it falls in
4. Tell the agent which skills and rules to load

## Agents Table

> This table is empty because agents have not been created yet.
> Once you read the codebase and create agents in `agents/`, fill in this table.

| Task Type | Assign To | Load Skills | Load Rules |
|-----------|-----------|-------------|------------|
| _example: API work_ | _backend agent_ | _python, database_ | _architecture, security_ |

## Multi-Agent Tasks

Some tasks need more than one agent working together. The manager coordinates the handoff.

| Task | Agent Order | How It Works |
|------|------------|--------------|
| _example: full-stack feature_ | _frontend → backend → QA_ | _Frontend builds UI, backend builds API, QA tests both_ |

## Edge Cases

- **Task doesn't fit any agent** — Manager asks the user for clarification
- **Task spans multiple areas** — Manager splits it and coordinates between agents
- **Documentation only** — Any agent can handle it, prefer the one who knows the area
