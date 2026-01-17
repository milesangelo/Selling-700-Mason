# Update Task Command

You are updating a task in the Selling-700-Mason project.

## Input
Parse $ARGUMENTS to extract:
- Task name
- Progress update text
- Status (optional: "done", "in progress", "pending"; defaults to "in progress")

Expected format: `<task name> | <progress note> | <status>`

## Steps

1. Use Glob to find all task phase files in the `tasks/` directory (e.g., `tasks/*.md`)

2. Use Grep to search each phase file for the task name to determine which file contains this task

3. Once you locate the correct phase file:
   - Read the file
   - Find the task's checklist item (e.g., `- [ ] Task Name` or `- [x] Task Name`)
   - Check if a "Progress Updates:" subsection exists immediately after the task item
   - If it doesn't exist, create it with proper indentation
   - Add a new update entry in the format:
     ```
     - [YYYY-MM-DD] <progress note> (Status: <status>)
     ```
   - Write the updated content back to the phase file

4. Update the `status.md` file:
   - Read the file
   - Locate or create a "## Recent Updates" section
   - Append the update in the format:
     ```
     - [YYYY-MM-DD] <Task Name>: <progress note> (Status: <status>)
     ```
   - Write the updated content back

5. Output ONLY a JSON object with these fields:
   ```json
   {
     "phase_file_path": "path/to/updated/file.md",
     "updated_phase_file_contents": "full updated markdown content",
     "status_update_snippet": "- [YYYY-MM-DD] Task: note (Status: status)"
   }
   ```

## Notes
- Use today's date (YYYY-MM-DD format) for all timestamps
- If status is not provided in $ARGUMENTS, default to "in progress"
- Preserve existing formatting and indentation in the files
- The Progress Updates subsection should be indented under the task item

## Example

Input: `/update-task Research zoning laws | Completed initial research on R3 zoning | done`

Output:
```json
{
  "phase_file_path": "tasks/phaseA.md",
  "updated_phase_file_contents": "# Phase A Tasks\n\n- [x] Research zoning laws\n  Progress Updates:\n  - [2026-01-17] Completed initial research on R3 zoning (Status: done)\n\n- [ ] Another task",
  "status_update_snippet": "- [2026-01-17] Research zoning laws: Completed initial research on R3 zoning (Status: done)"
}
```
