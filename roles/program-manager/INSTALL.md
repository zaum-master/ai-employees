# Program Manager installation contract

The setup agent provisions Hermes and creates a new Program Manager instance
from this template. It must inspect current Hermes documentation and the
installed version before choosing commands or configuration keys.

## Required instance artifacts

Create these runtime-local files from the templates:

- `IDENTITY.md`
- `OPERATING_BRIEF.md`
- `SOUL.md`
- `CHANNEL_POLICY.md`
- `.employee-data/tasks.json`

Keep secrets in the runtime's local secret environment file. Keep task state
under `.employee-data/`, outside Git. The setup agent may create these files;
the Program Manager may update its local task state but may not rewrite its own
identity, operating rules, runtime configuration, or channel policy.

Render the generated `SOUL.md` with the behavioral contract in `ROLE.md`; the
live employee must not depend on this source template remaining available after
installation.

## Health checks

Before declaring setup complete, verify:

1. Hermes starts with the generated instance configuration.
2. The configured model can complete a small authenticated request.
3. The selected control channel receives and returns one test message.
4. The local task store accepts the first project snapshot.

Each result must come from the current runtime or integration response. A
written configuration file alone is not proof that the employee is live.
