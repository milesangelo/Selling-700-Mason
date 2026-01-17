# 🏁 Next Task

Returns the best next actionable task based on the current plan and status.

---

Read `plan.md` and `status.md` from the repository root. Analyze the current project state, completed tasks, in-progress tasks, and remaining work.

Based on this analysis, identify and return **one single actionable task** that should be done next. The task should:
- Be the highest priority item that is not yet started
- Be logically feasible given what has been completed
- Be specific and actionable

Output format:
```
🏁 NEXT TASK:
[Task description]

Phase: [Phase name]
Reason: [Brief explanation of why this is the next priority]
```

Do not list multiple tasks. Return only the single best next action.
