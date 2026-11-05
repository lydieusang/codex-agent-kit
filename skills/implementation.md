# Implementation

Use this workflow for any repository file edit, including code, configuration,
tests, and documentation. Check the approval gates in `.agents/AGENTS.md`.

Enter this workflow only when the user explicitly asks to change repository
files, when it is the approved next workflow under `.agents/AGENTS.md`, or when
it is needed within an explicitly authorized LOOP.
A question, bug report, expected-behavior statement, or diagnostic request is
not an implementation request.

Before substantial or risky changes, perform the impact analysis described in
[Planning](planning.md), reusing current findings when available.

Before editing outside LOOP, give a concise inline plan: intended behavior,
files to change, validation, and optional broader cleanup that will not be
performed. Ask for approval and wait. A request to change a file is not
approval of the plan. Inside LOOP, check that the edit fits its authorization
and proceed without another approval.

Once authorized, implement the smallest safe diff. Do not turn a small request
into a formal specification.

For planned work, follow the authorized specification and plan. If an
active feature workspace exists, use its task order and update task status,
handoff, and evaluation records at meaningful checkpoints.

Validate in proportion to the risk: run targeted tests and relevant lint/type
checks when available; otherwise state what was checked and what remains unrun.
For bug fixes, reproduce the failure before editing when feasible and add focused
regression tests where practical. Confirm they fail for the original bug and pass
with the fix, and verify affected behavior using the relevant regression checks.
Report any reproduction, test, or validation gaps and their reasons.
At completion, report the behavior changed, files changed, validation, and any
intentionally deferred work.
