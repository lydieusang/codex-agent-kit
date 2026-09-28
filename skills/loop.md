# LOOP

Use only when the user explicitly delegates autonomous end-to-end execution.
Task size, complexity, or approval of a normal workflow does not activate LOOP.
LOOP orchestrates the existing workflows; it does not replace their skills.

First inspect the repository and establish the authorized goal, scope,
constraints, and verifiable completion criteria. State material assumptions.
Select and read only the workflow skills needed for the goal. There is no fixed
sequence or mandatory workspace; use the core optional workspace rule.

The initial LOOP authorization takes precedence over every selected skill's
routine approval gate for necessary, in-scope, reversible repository-local
work. Do not request approval between stages, including for in-scope fixes.
Follow each skill's other instructions. After each meaningful stage, reassess
the goal and choose the next useful workflow or finish. Skip stages that add
no value.

IMPLEMENTATION owns repository edits, including documentation edits. EVALUATION
remains read-only: take its findings into a separate IMPLEMENTATION correction,
then validate and evaluate again as needed. Standalone documentation uses
DOCUMENTATION. Use CLEANUP only when the LOOP request explicitly includes
cleanup and it materially helps meet the goal; keep it behavior-preserving.

Run proportionate tests, lint, type checks, builds, or other relevant validation.
Diagnose and correct in-scope failures until the criteria pass or escalation is
needed.

Pause for a user decision when the goal is materially ambiguous; meeting it
needs meaningful scope expansion; new evidence invalidates an important
assumption or direction; an unexpected architecture, public API, schema, or
significant dependency decision arises; security or privacy needs human
judgment; an action is destructive or difficult to reverse; validation exposes
an out-of-scope problem; repeated attempts make no meaningful progress; or the
completion criteria cannot reasonably be met. After resolution, resume the
same LOOP.

Follow core Git safety. LOOP alone does not authorize committing, pushing,
force-pushing, branch deletion, history rewriting, deployment, or other
external or destructive actions. Perform any of these only when the user
specifically authorizes it.

Finish with a concise summary of changes, validation evidence, remaining
limitations, and Git state.
