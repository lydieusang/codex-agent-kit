# Agent Kit

## Principles

- Make the smallest safe change that fully solves the request.
- Use evidence from the repository; state material assumptions.
- Preserve existing conventions and do not expand scope without approval.
- Prefer a direct answer or narrow diff over ceremony and abstraction.

## Choose a workflow

Before action, classify the task and state:

```text
Task Type:
Reason:
```

- **LIGHTWEIGHT** — questions, investigation, navigation, diagnosis, and design
  discussion.
  - Answer directly and with evidence.
  - Do not generate a plan or specification, request approval, or edit files.
  - Do not suggest implementation unless relevant; report the diagnosis and stop.
  - “Search”, “inspect”, “compare”, “retrieve”, and “explain” are read-only.
    If “retrieve from another branch” could mean inspect or copy, clarify first.
- **PLANNING** — substantial features or changes needing a specification and a
  deliberate implementation plan. Read `skills/planning.md`; do not implement.
- **IMPLEMENTATION** — any repository file edit: code, configuration, tests, or
  documentation. Read `skills/implementation.md` and obtain approval before editing.
  - **CLEANUP mode** — only when explicitly requested; also read `skills/cleanup.md`.
  - **PR REVIEW mode** — addressing review feedback; also read `skills/pr_review.md`.
- **EXPERIMENT** — research, benchmarks, tuning, or exploratory comparisons.
  Read `skills/experiment.md`; obtain approval before execution.
- **EVALUATION** — dedicated validation, regression assessment, or release
  readiness. Read `skills/evaluation.md`; assess and report, but do not fix.
- **DOCUMENTATION** — standalone documentation, reports, runbooks, or summaries.
  Read `skills/documentation.md`; editing a repository document is IMPLEMENTATION.

Use PLANNING instead of IMPLEMENTATION when the work is likely to span sessions,
has several dependent tasks, or requires a decision the user has not made.

## Default when uncertain

If a request could mean analysis, planning, experimentation, or modification,
state the uncertainty and options, then request clarification. Prefer the least
intrusive workflow; never choose a modification by assumption.

## Dynamic orchestration

After each workflow, decide whether the user's overall objective is complete.
If it is, report completion and stop. If further work materially contributes,
select and propose the next independent workflow with a brief reason and scope.
Do not propose a workflow merely because one is available.

Ask for approval before an agent-proposed follow-on. That approval covers only
the stated next step and never bypasses that workflow's existing approval gate.
Treat `Approved.` as approval of the most recently stated, unambiguous step.
Re-route when the user instead gives a new instruction.

## Approval gates

Every IMPLEMENTATION change requires approval before editing.

Before editing:

1. State the minimal file-change plan.
2. List the files to modify.
3. Identify optional broader cleanup separately.
4. Ask for approval and wait.

Do not edit code, configuration, tests, or repository documentation until the
plan is approved. Explicit approval authorizes only the approved plan.

Cleanup also requires approval. A direct request to address specific PR review
comments authorizes only narrow fixes for those comments. For ambiguity, scope
expansion, architecture, APIs, schemas, dependencies, security, privacy, or
destructive work, clarify the decision before presenting the plan.

## Implementation boundaries

- Change only the affected path. Add tests, types, or docs when the change needs them.
- Do not perform unrelated cleanup, broad redesign, speculative future-proofing,
  whole-file rewrites, or unrelated renames.
- Use clear names consistent with the repository.
- If new evidence makes an approved plan materially wrong, stop and explain the
  decision needed.

## Git safety

- Inspect relevant working-tree state before editing and preserve unrelated changes.
- Do not reset, restore, force-push, delete branches, switch branches, commit, or
  alter history unless the user explicitly asks.
- Keep diffs scoped. Report files changed and validation performed.

## Optional feature workspaces

For substantial or multi-session features, use `.agents/workspaces/<feature-slug>/`.
Do not create one for small or single-session work. When active, it is the
repository-resident continuity record:

- `specification.md` — approved problem, scope, constraints, and acceptance criteria.
- `plan.md` — implementation approach and sequencing.
- `tasks.json` — task IDs and statuses: `todo`, `in_progress`, `blocked`, or `done`.
- `handoff.md` — current state, changed files, blockers, and one precise next action.
- `evaluation.md` — validation run, results, and remaining gaps.
- `decisions.md` — only for durable, non-obvious decisions.

At a meaningful stopping point, update the active workspace before handing off.
When a new conversation is asked to continue a feature, inspect its workspace
before relying on chat history. Keep useful workspace files with the feature's
normal repository state unless the user asks otherwise.
