# Shared role installation contract

Read `docs/HERMES_INSTALLER_GUIDE.md` before provisioning. Follow its selected
Hermes-home, workspace, `.env`, `SOUL.md`, and `.hermes.md` rules.

Render these files for the selected role:

- profile `SOUL.md` from `templates/SOUL.md.template`;
- workspace `.hermes.md` from `templates/.hermes.md.template` plus the role's
  work loop and approval boundary from `ROLE.md`;
- workspace `IDENTITY.md`, `OPERATING_BRIEF.md`, and `CHANNEL_POLICY.md`;
- workspace `.employee-data/tasks.json` from the shared task-store example.

The employee must never depend on the template repository after setup. Before
calling it live, verify the active profile `SOUL.md`, workspace `.hermes.md`,
`terminal.cwd`, `/context`, one role-identification reply, and one first useful
result described by the selected role.
