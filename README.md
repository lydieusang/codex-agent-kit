# Agent Kit v2

A small workflow kit for Codex and other coding agents. The repository-root
`AGENTS.md` is the entrypoint; it delegates to `.agents/AGENTS.md`, which routes
work to focused skills only when needed.

```text
my-project/
├── AGENTS.md
├── .agents/
│   ├── AGENTS.md
│   ├── README.md
│   ├── skills/
│   └── workspaces/
├── src/
└── tests/
```

## Daily use

Use normal requests. The kit selects a lightweight response, a small inline
implementation plan, or formal planning based on scope and risk. No copied
launcher prompts are required.

The core policy stays intentionally short. Workflow-specific detail lives in
individual files under `skills/`; an agent reads only the skill it needs.

## Optional feature workspaces

Use `.agents/workspaces/<feature-slug>/` only for substantial or multi-session
features. Do not create one for a small fix. Its purpose is continuity from
repository state, not process overhead.

Create only useful files:

- `specification.md` — approved objective, scope, constraints, and acceptance criteria.
- `plan.md` — approach and ordered steps.
- `tasks.json` — machine-readable task status.
- `handoff.md` — latest state, blockers, and exact next action.
- `evaluation.md` — validation results and remaining gaps.
- `decisions.md` — durable decisions that are not obvious from the code.

When continuing such a feature in a new conversation, read its workspace first.
Update `handoff.md` and task status before stopping at a meaningful boundary.
