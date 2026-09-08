# Planning

Use this workflow for a substantial feature, a multi-session change, or work
with unresolved product or technical decisions.

Inspect the relevant code and existing instructions first. Then define:

1. the objective and current context;
2. assumptions, scope, and explicit non-goals;
3. constraints, risks, and open decisions;
4. acceptance criteria and proportionate validation; and
5. a minimal ordered implementation plan.

State alternatives only when they meaningfully affect cost, risk, or behavior.
Recommend the smallest viable approach. Ask for approval before implementation.
Planning approval approves the direction, not edits; IMPLEMENTATION still needs
its file-change plan approved before editing.
Do not edit repository files while planning; return to IMPLEMENTATION only after
the user approves its file-change plan.

Recommend an optional feature workspace when the work will likely span sessions
or has multiple dependent tasks. After approval, initialize only the useful
workspace files. Use this `tasks.json` shape:

```json
{
  "feature": "feature-slug",
  "updated": "YYYY-MM-DD",
  "tasks": [
    { "id": "T1", "title": "Short task", "status": "todo", "notes": "" }
  ]
}
```
