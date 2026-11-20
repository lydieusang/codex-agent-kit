# LOOP

LOOP orchestrates existing workflow skills under explicit end-to-end
authorization; normal workflow approval does not activate it.

Inspect the repository; define the authorized goal, scope, constraints,
assumptions, and minimal verifiable completion criteria from user intent and
repository evidence. Do not invent features. Honor user checkpoints and
restrictions. Stop when proportionate validation meets the criteria. Load only
needed skills; no fixed workflow sequence or mandatory workspace.

Within authorized scope, execute reversible repository-local work and fixes
without intermediate approvals; retain other skill rules. Recheck completion
after meaningful stages. Iterate only on evidenced unmet requirements, defects,
or regressions—not optional improvements or unrelated findings.

IMPLEMENTATION owns repository edits, including documentation edits. EVALUATION
remains read-only: take its findings into a separate IMPLEMENTATION correction,
then validate and evaluate again as needed. Standalone documentation uses
DOCUMENTATION. Use CLEANUP only when the LOOP request explicitly includes
cleanup and it materially helps meet the goal; keep it behavior-preserving.

Validate against criteria and changed risk areas with proportionate tests,
lint, type checks, or builds. Reuse evidence; rerun checks when changes warrant
it. Verify each correction's intended effect. Escalate on repeated lack of
measurable progress, not merely on task difficulty.

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
