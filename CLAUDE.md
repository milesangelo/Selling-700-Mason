# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **project management repository** for preparing a house (700 Mason) for sale. It is NOT a software project—it contains markdown-based task tracking, status monitoring, and planning documents for a real estate renovation workflow.

The repository uses a phased approach to organize work:
- **Phase A**: Convert Excess → Cash & Space (liquidate unused items)
- **Phase B**: Kill Inspection Red Flags (safety/mechanical issues)
- **Phase C**: Visual Finish + Value Add (hardwood, range hood)
- **Phase D**: Pre-Inspection Awareness & Minor Cleanup

## Repository Structure

```
Selling-700-Mason/
├── plan.md                      # Strategic master plan (rarely changes)
├── status.md                    # Current snapshot (updated weekly/at milestones)
├── tasks/
│   ├── phaseA.md               # Phase A task checklist
│   ├── phaseB.md               # Phase B task checklist
│   ├── phaseC.md               # Phase C task checklist
│   └── phaseD.md               # Phase D task checklist
└── .claude/commands/            # Custom slash commands
    ├── status.md               # View project status
    ├── next.md                 # Get next actionable task
    ├── add-task.md             # Add task to phase
    ├── update-task.md          # Update task progress
    ├── summarize-phase.md      # Summarize phase completion
    └── create-plan-update.md   # Generate plan update
```

## Custom Slash Commands

This project includes custom Claude Code commands for task management. These are user-invocable skills defined in `.claude/commands/`:

### `/status`
Reads `plan.md`, `status.md`, and `tasks/*.md` to provide comprehensive status with:
- Current phase
- Completed tasks (✅)
- In progress tasks (🔄)
- Not started tasks (⬜)
- Overall progress percentage

### `/next`
Analyzes project state and returns **one single actionable task** that should be done next, with phase and reasoning.

### `/add-task`
Adds a new task to a phase file.
- **Usage**: `/add-task <task description>` or `/add-task <task description> | <phase>`
- Automatically determines phase if not specified

### `/update-task`
Records progress on a task and updates both the phase file and `status.md`.
- **Usage**: `/update-task <task name> | <progress note> | <status>`
- Status options: `done`, `in progress`, `pending` (defaults to "in progress")
- Adds timestamped progress updates under task items
- Creates/updates "Recent Updates" section in `status.md`

### `/summarize-phase`
Generates summary of completed work and remaining tasks for a phase.
- **Usage**: `/summarize-phase <phase>`

### `/create-plan-update`
Generates formatted plan update with completed tasks and next steps.

## Working with Task Files

### Task File Format
Each phase file (`tasks/phaseA.md`, etc.) contains:
- Markdown checkboxes: `- [ ]` for incomplete, `- [x]` for complete
- Grouped tasks under `###` subheadings
- Optional "Progress Updates:" subsections with dated entries

### Updating Tasks
When using `/update-task`, the command:
1. Searches all phase files to locate the task
2. Adds a progress update entry under the task with format:
   ```
   - [YYYY-MM-DD] <progress note> (Status: <status>)
   ```
3. Updates `status.md` with the same information

### Status Tracking Philosophy
- **plan.md**: Strategic overview (rarely changes)
- **status.md**: Current snapshot (updated weekly or at major milestones)
- **tasks/*.md**: Granular checklists (updated as work progresses)

All updates should include dates and status indicators for clear project history.

## Important Guidelines

### No Software Build Commands
There are no build, test, lint, or compilation commands. This is a document-based project management system, not a codebase.

### Phase Sequencing
Phases must be completed sequentially. Each phase builds on the previous one:
- Phase A funds and clears space for Phase B
- Phase B eliminates deal-breakers before value-add work
- Phase C adds visual improvements
- Phase D is final prep

### Documentation Updates
When updating task or status files:
- Use ISO date format (YYYY-MM-DD)
- Maintain checkbox format for tasks
- Keep progress notes concise but specific
- Preserve existing formatting and indentation

### Custom Command Behavior
The custom commands expect:
- Phase files to be in `tasks/` directory named `phaseA.md`, `phaseB.md`, etc.
- Status file at root: `status.md`
- Plan file at root: `plan.md`
- Date-stamped progress updates for traceability

## Timeline Philosophy

The project prioritizes **doing the right work in the right order** over arbitrary deadlines. Quality and proper sequencing prevent rework.

Estimated timeline: 6-10 weeks total depending on contractor availability and weather.
