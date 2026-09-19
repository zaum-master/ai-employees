# Shared local task store

Create `.employee-data/tasks.json` in the employee workspace from
`tasks.json.example`. It is the initial source of truth for the work the
employee tracks.

Each record holds a stable ID, work item, desired outcome, status, owner when
known, next action, blocker or decision, due date only when sourced, evidence,
and dated history. The employee records uncertainty rather than inventing an
owner, deadline, approval, or completion.
