# Hermes installer guide

Read this guide before installing or repairing a Hermes AI employee. It gives
the stable mental model. Then inspect the current Hermes documentation and the
installed version before selecting commands or configuration keys.

## Hermes has a profile and a workspace

A Hermes **profile** is the employee's persistent home: its model
configuration, secrets, persona, memory, sessions, skills, gateway state, and
logs. A **workspace** is the directory where that employee does its work.
They are different locations.

| Installation state | Employee's Hermes home | Employee workspace |
| --- | --- | --- |
| Hermes was just installed | The fresh default home, normally `~/.hermes/` | Create a dedicated workspace, normally `~/.hermes/workspaces/<employee-id>/` |
| Hermes already existed | A new named profile, normally `~/.hermes/profiles/<employee-id>/` | Create a dedicated workspace, normally `~/.hermes/workspaces/<employee-id>/` |

Never assume a path only from this table. Confirm the selected profile's actual
`HERMES_HOME` and `terminal.cwd` using the installed Hermes documentation and
configuration commands.

## Which file controls what

### In the selected Hermes home

| File or directory | Purpose | Installer rule |
| --- | --- | --- |
| `config.yaml` | Non-secret model, gateway, tool, and working-directory settings | Change only documented settings for the selected profile. |
| `.env` | Provider keys, channel tokens, and other secrets | Write supplied secrets only here. Never print, commit, or copy them into workspace files. |
| `SOUL.md` | The employee's primary identity, loaded first in every new session | Write the rendered employee persona here. A workspace `SOUL.md` does not set the live persona. |
| `memories/`, `sessions/`, `state.db`, `skills/`, `cron/`, `logs/` | Profile-scoped runtime state | Never copy another employee's state into this employee. |

For a fresh installation the selected home is normally `~/.hermes/`. For a
named profile it is normally `~/.hermes/profiles/<employee-id>/`. Hermes uses
`HERMES_HOME`, not the workspace path, to find the selected profile's
`SOUL.md`, configuration, memory, and channel state.

### In the employee workspace

| File or directory | Purpose | Installer rule |
| --- | --- | --- |
| `.hermes.md` | The employee's active work instructions | Render the role work-loop template here. Hermes prefers this file over `AGENTS.md`. |
| `OPERATING_BRIEF.md` | Buyer-specific role, outcomes, first project, and work surfaces | Render from the buyer's intake. |
| `CHANNEL_POLICY.md` | Control channel, read scope, allowlist, and outbound boundary | Render before a channel is connected. |
| `IDENTITY.md` | Human-readable instance record | Keep aligned with the selected profile and role. It is not the live Hermes identity slot. |
| `.employee-data/tasks.json` | Local Program Manager task record | Create before the first project update. |

`SOUL.md` and `.hermes.md` are intentionally separate. Put identity and
durable communication behavior in the selected profile's `SOUL.md`; put the
employee's project-specific work loop and paths in the workspace `.hermes.md`.

## Installation decision

1. Check whether Hermes already works on the buyer's machine.
2. If it does not exist, install Hermes using the current official procedure.
   Configure the fresh default profile as the first employee; do not create a
   second profile merely because this is an employee.
3. If it already exists, create a dedicated named profile for the employee.
   Do not overwrite the buyer's default profile, its `SOUL.md`, secrets,
   memories, or channels.
4. Create the employee workspace and set the selected profile's `terminal.cwd`
   to it.
5. Render the role persona into the selected profile's `SOUL.md` and the role
   work loop into the workspace `.hermes.md`.
6. Render the operating brief, channel policy, identity record, and local task
   record into the workspace.
7. Configure the selected profile's provider and channel, keeping secrets in
   its `.env`.

## Verify the files Hermes actually loaded

Do not call setup successful because files exist on disk. In the selected
profile and a fresh control-channel session, verify all of the following:

1. `terminal.cwd` resolves to the employee workspace.
2. The selected profile's `SOUL.md` contains the rendered employee persona.
3. The workspace `.hermes.md` contains the rendered role work loop.
4. Hermes' `/context` output reports those files as loaded, not shadowed,
   blocked, unreadable, or truncated.
5. Ask, “What do you do?” The reply identifies the named role rather than a
   generic Hermes assistant.
6. Send one genuine project update and verify that the Program Manager creates
   and saves the expected project snapshot.

Hermes builds its system prompt at session start. After changing `SOUL.md` or
`.hermes.md`, start a fresh session before judging the result. Do not alter
Hermes source code to customize one employee; use these supported profile and
workspace files.
