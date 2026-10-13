# LOOP

Use only when the user explicitly delegates autonomous end-to-end execution.
Task size, complexity, or approval of a normal workflow does not activate LOOP.
LOOP orchestrates the existing workflows; it does not replace their skills.

First inspect the repository and establish the authorized goal, scope,
constraints, and smallest set of verifiable completion criteria; state material
assumptions. Those criteria are the stopping condition: finish when
proportionate validation shows they are satisfied, rather than continuing
because more work is possible. Select and read only the workflow skills needed
for the goal. There is no fixed sequence or mandatory workspace; use the core
optional workspace rule.

The initial LOOP authorization takes precedence over every selected skill's
routine approval gate for necessary, in-scope, reversible repository-local
work. Do not request approval between stages, including for in-scope fixes;
follow each skill's other instructions. After each meaningful stage, check the
criteria and finish if they pass. Continue only when concrete evidence shows an
authorized requirement is unmet or a defect, regression, or validation failure
needs correction. Optional improvements, unsupported concerns, and unrelated
findings do not justify another iteration.

IMPLEMENTATION owns repository edits, including documentation edits. EVALUATION
remains read-only: take its findings into a separate IMPLEMENTATION correction,
then validate and evaluate again as needed. Standalone documentation uses
DOCUMENTATION. Use CLEANUP only when the LOOP request explicitly includes
cleanup and it materially helps meet the goal; keep it behavior-preserving.

Run proportionate tests, lint, type checks, builds, or other relevant
validation against the criteria and changed risk areas. Reuse relevant evidence
and avoid equivalent checks unless a change or specific failure makes them
informative again. For each correction, identify and verify the evidence it
should change. Continue difficult work while attempts materially narrow the
cause, resolve a failure, or increase confidence; otherwise, treat repeated
lack of progress as non-convergence and escalate rather than looping
indefinitely.

Pause for a user decision when the goal is materially ambiguous; meeting it
needs meaningful scope expansion; new evidence invalidates an important
assumption or direction; an unexpected architecture, public API, schema, or
significant dependency decision arises; security or privacy needs human
judgment; an action is destructive or difficult to reverse; validation exposes
an out-of-scope problem; evidence shows non-convergence; or the completion
criteria cannot reasonably be met. After resolution, resume the same LOOP.

Follow core Git safety. LOOP alone does not authorize committing, pushing,
force-pushing, branch deletion, history rewriting, deployment, or other
external or destructive actions. Perform any of these only when the user
specifically authorizes it.

Finish with a concise summary of changes, validation evidence, remaining
limitations, and Git state.
