# 700 Mason — House Sale Preparation Project

Project management repository for preparing 700 Mason for sale. This repo tracks all tasks, progress, and documentation for a phased approach to property preparation.

## Project Structure

```
Selling-700-Mason/
├── readme.md                    # This file
├── plan.md                      # Master plan with phase details
├── status.md                    # Current status and progress tracking
├── tasks/
│   ├── phaseA.md               # Phase A: Convert Excess → Cash & Space
│   ├── phaseB.md               # Phase B: Kill Inspection Red Flags
│   ├── phaseC.md               # Phase C: Visual Finish + Value Add
│   └── phaseD.md               # Phase D: Pre-Inspection Awareness & Minor Cleanup
└── .claude/commands/            # Custom slash commands for task management
```

## Four-Phase Strategy

### Phase A: Convert Excess → Cash & Space
Liquidate unused tools, materials, and equipment to fund renovation work and clear workspace.

### Phase B: Kill Inspection Red Flags
Eliminate critical safety, mechanical, and structural issues that would flag during inspection.

### Phase C: Visual Finish + Value Add
Complete high-visibility improvements (hardwood refinishing, range hood, etc.) that enhance buyer perception.

### Phase D: Pre-Inspection Awareness & Minor Cleanup
Self-identify inspection items, address minor issues, and prepare disclosure documentation.

## Custom Slash Commands

This project includes custom Claude Code commands for efficient task management:

### `/status`
View current project status and progress across all phases.

### `/next`
Identify the next actionable task to work on.

### `/add-task`
Add a new task to a specific phase file.

**Usage:** `/add-task <phase> | <task description>`

### `/update-task`
Record progress on an existing task and update status.

**Usage:** `/update-task <task name> | <progress note> | <status>`

Status options: `done`, `in progress`, `pending`

### `/summarize-phase`
Generate a summary of completed work and remaining tasks for a specific phase.

**Usage:** `/summarize-phase <phase>`

### `/create-plan-update`
Generate a formatted plan update with completed tasks and next steps.

## Getting Started

1. Review the [master plan](plan.md) to understand the overall strategy
2. Check [status.md](status.md) for current progress
3. Use `/next` to identify your next action
4. Use `/update-task` to record progress as you work

## Timeline

Estimated total duration: 6-10 weeks depending on contractor availability and weather.

The project prioritizes doing the right work in the right order over arbitrary deadlines. Each phase builds on the previous one to minimize rework and maximize quality.

## Documentation Philosophy

- **plan.md**: Strategic overview (rarely changes)
- **status.md**: Current snapshot (updated weekly or at major milestones)
- **tasks/*.md**: Granular checklists (updated as work progresses)

All updates should be traceable with dates and status indicators to maintain clear project history.
