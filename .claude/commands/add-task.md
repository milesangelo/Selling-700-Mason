# ✏️ Add Task

Adds a new task to the appropriate phase task list.

---

Arguments: $ARGUMENTS

Parse the arguments to extract:
1. Task description (required)
2. Phase name (optional, format: "Phase A", "Phase B", etc.)

Steps:
1. If a phase is specified in parentheses at the end (e.g., "(Phase A)"), extract it
2. If no phase is specified, determine the most appropriate phase based on `plan.md` and current project status
3. Identify the corresponding task file in `tasks/` directory (e.g., `tasks/phase-a.md`, `tasks/phaseA.md`, etc.)
4. Add a new unchecked checkbox item to that file: `- [ ] [task description]`
5. Confirm the task was added with a success message

Output format:
```
✅ Task added to [Phase Name]:
- [ ] [task description]
```

If the tasks file doesn't exist, create it with proper formatting first.
