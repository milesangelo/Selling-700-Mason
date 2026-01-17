# 📌 Summarize Phase

Provides a summary of completed vs incomplete tasks for a specific phase.

---

Arguments: $ARGUMENTS

Expected argument: Phase name (e.g., "Phase A", "A", "phase-a")

Steps:
1. Parse the phase name from the arguments
2. Locate the corresponding task file in `tasks/` directory
3. Count checked items (done) vs unchecked items (not done)
4. List all tasks with their status

Output format:
```
📌 PHASE [NAME] SUMMARY

✅ Completed: [X] tasks
⬜ Remaining: [Y] tasks
📊 Progress: [X/Total] ([percentage]%)

--- Tasks ---
[✅/⬜] Task 1
[✅/⬜] Task 2
...
```

If the phase file is not found, list available phases from the `tasks/` directory.
