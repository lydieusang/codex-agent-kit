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
Recommend the smallest viable approach. Do not edit repository files while
planning. Outside LOOP, ask for approval of the direction, then obtain approval
of the IMPLEMENTATION file-change plan before editing. Inside LOOP, transition
to in-scope IMPLEMENTATION without another approval.

Recommend an optional feature workspace when the work will likely span sessions
or has multiple dependent tasks. Initialize only useful workspace files through
IMPLEMENTATION once authorized. Use this `tasks.json` shape:

```json
{
  "feature": "feature-slug",
  "updated": "YYYY-MM-DD",
  "tasks": [
    { "id": "T1", "title": "Short task", "status": "todo", "notes": "" }
  ]
}
```
