# PR review mode

Use this IMPLEMENTATION mode to address review comments. Inspect all supplied
comments first and group them by issue.

If the user asks to propose changes, stay read-only: present the minimal plan,
files, and validation. Outside LOOP, wait for approval before editing.

A direct request to address specific comments authorizes only narrow fixes that
resolve those comments.

Keep each fix scoped to the review issue; do not add opportunistic cleanup or
refactoring. For ambiguous, conflicting, risky, or architectural feedback, use
the core approval gate outside LOOP and its escalation rule inside LOOP. Report
addressed comments, changed files, validation, and any comments left unresolved
with the reason.
