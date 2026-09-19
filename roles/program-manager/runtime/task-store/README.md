# Local task store

The initial Program Manager uses one local Jira-like task record. It avoids
asking the buyer for Jira, Linear, or other task-system credentials during
setup.

Create `.employee-data/tasks.json` from `tasks.json.example` in the runtime
workspace. It is the only task source of truth for this template.

Each task carries:

- a stable local ID;
- project and desired outcome;
- title and concise context;
- one current owner when known;
- status: `open`, `in_progress`, `blocked`, `waiting`, or `done`;
- next action;
- blocker or decision needed;
- due date only when sourced;
- source reference and observed time when available;
- a dated history of material changes.

The Program Manager reads the complete relevant conversation before changing a
task. It records unknowns as unknowns and does not mark work done without
clear, attributable evidence. A later role version may synchronize this local
record to a buyer's chosen task platform; it must not make a second independent
record that can drift.

