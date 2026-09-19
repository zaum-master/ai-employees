# Program Manager installation contract

The setup agent provisions Hermes and creates a new Program Manager instance
from this template. It must inspect current Hermes documentation and the
installed version before choosing commands or configuration keys.

## Required instance artifacts

Create these runtime-local files from the templates:

- `IDENTITY.md`
- `OPERATING_BRIEF.md`
- `CHANNEL_POLICY.md`
- workspace `AGENTS.md`
- `.employee-data/tasks.json`

Keep secrets in the runtime's local secret environment file. Keep task state
under `.employee-data/`, outside Git. The setup agent may create these files;
the Program Manager may update its local task state but may not rewrite its own
identity, operating rules, runtime configuration, or channel policy.

Render `SOUL.md` with the behavioral contract in `ROLE.md` and write it to the
active Hermes profile's identity location. Do not leave it only in the employee
workspace: Hermes must load it in each live channel session. Render the
workspace `AGENTS.md` as the employee's day-to-day work loop. Before choosing
paths, inspect the installed Hermes version and its current profile and prompt
assembly documentation. The live employee must not depend on this source
template remaining available after installation.

## Health checks

Before declaring setup complete, verify:

1. Hermes starts with the generated instance configuration.
2. The configured model can complete a small authenticated request.
3. The selected control channel receives and returns one test message.
4. The local task store accepts the first project snapshot.
5. In a fresh control-channel conversation, the employee answers “What do you
   do?” as the named Program Manager, not as a generic Hermes assistant. It
   should name its role and first project when known, or ask for the first
   project update. A stock transport greeting does not count as this check.
6. A genuine project update produces a saved project snapshot with the
   objective, current status, owner, next action, blocker or decision, and
   unknowns.

Each result must come from the current runtime or integration response. A
written configuration file alone is not proof that the employee is live.
