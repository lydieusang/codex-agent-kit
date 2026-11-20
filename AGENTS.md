# Agent Kit

## Principles

- Make the smallest safe change that fully solves the request.
- Use evidence from the repository; state material assumptions.
- Preserve existing conventions and do not expand scope without approval.
- Prefer a direct answer or narrow diff over ceremony and abstraction.

## Documentation and Markdown requirements

Apply these rules whenever creating or editing documentation and Markdown:

- Write concise, task-focused documents; give each file one purpose.
- State facts once and link to their source of truth.
- Preserve runnable commands, key results, limitations, acceptance status, and
  evidence links; remove repetition, stale counts, and session history.
- Reread and shorten without losing essential information.

## Choose a workflow

Before action, classify the task and state:

```text
Task Type:
Reason:
```

- **LIGHTWEIGHT** — questions, investigation, navigation, diagnosis, and design
  discussion.
  - Answer with evidence; do not plan, request approval, or edit.
  - Treat search, inspection, comparison, and retrieval as read-only; clarify
    ambiguous requests to retrieve content from another branch.
- **PLANNING** — substantial features or changes needing a specification and a
  deliberate implementation plan. Read `skills/planning.md`; do not implement.
- **IMPLEMENTATION** — any repository file edit: code, configuration, tests, or
  documentation. Read `skills/implementation.md` and follow the approval rules
  below.
  - **CLEANUP mode** — only when explicitly requested; also read `skills/cleanup.md`.
  - **PR REVIEW mode** — addressing review feedback; also read `skills/pr_review.md`.
- **EXPERIMENT** — research, benchmarks, tuning, or exploratory comparisons.
  Read `skills/experiment.md` and follow the approval rules below.
- **EVALUATION** — dedicated validation, regression assessment, or release
  readiness. Read `skills/evaluation.md`; assess and report, but do not fix.
- **DOCUMENTATION** — standalone documentation, reports, runbooks, or summaries.
  Read `skills/documentation.md`; editing a repository document is IMPLEMENTATION.
- **LOOP** — explicit autonomous end-to-end delegation, by name or natural
  language. Read `skills/loop.md`. Size, multiple stages, or a complete-feature
  request alone do not authorize LOOP.

Outside LOOP, use PLANNING instead of IMPLEMENTATION when the work is likely to
span sessions, has several dependent tasks, or requires a decision the user has
not made.

## Default when uncertain

When intent is ambiguous, clarify rather than assume permission to modify.
Without explicit autonomous delegation, use normal routing; offer LOOP as an
opt-in alternative only when materially useful.

## Dynamic orchestration

Outside LOOP, stop when the objective is met; otherwise propose only a useful
next workflow with reason and scope. Wait for approval of that step and honor
its gate. `Approved.` applies to the latest unambiguous proposal; new
instructions trigger re-routing. Inside LOOP, follow `skills/loop.md`.

## Approval gates

Outside LOOP, before IMPLEMENTATION (including CLEANUP), state the minimal
file-change plan, affected files, and optional broader cleanup separately.
Wait for approval before editing; approval covers only that plan.

A direct request to address specific PR review comments authorizes only narrow
fixes for those comments. For ambiguity, scope expansion, architecture, APIs,
schemas, dependencies, security, privacy, or destructive work, clarify the
decision before presenting the plan.

Inside LOOP, the initial authorization overrides routine skill approval gates
for necessary, in-scope, reversible repository-local work. Follow
`skills/loop.md` for escalation.

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
