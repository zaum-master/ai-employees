# Zaum AI Employees

This repository turns a capable setup agent—Claude, Codex, or a comparable
agent with terminal access—into an onboarding guide for a Zaum AI employee.

Program Manager is the first ready role. Point a setup agent at this directory
and ask it to begin. Codex reads `AGENTS.md`; Claude Code reads `CLAUDE.md`;
other agents should start with `AGENTS.md`.

When sharing a GitHub URL rather than opening a local checkout, use the exact
starter message in [`START_HERE.md`](START_HERE.md). It tells the agent to
retrieve the repository and begin by asking which AI employee the buyer wants
to create.

The guide learns the role from the buyer's job description, provisions a
Hermes employee on a durable runtime, configures the requested work surfaces,
and proves one useful first result. Customer credentials and live data stay in
the customer's local environment and are never committed to this repository.

## Ready roles

| Role | Status | Entry point |
| --- | --- | --- |
| Program Manager | Ready | `roles/program-manager/ROLE.md` |

The role catalog is `roles.json`. Add future employees, such as Supply
Manager, as separate role folders and catalog entries; do not turn the Program
Manager instructions into a collection of unrelated roles.

## What the first version does

- Uses the buyer's job description to create a role-specific operating brief.
- Chooses a verified persistent cloud runtime when one is available; otherwise
  installs Hermes on the buyer's machine.
- Uses OpenRouter with DeepSeek 0731 by default, unless the buyer supplies a
  supported preferred provider or model.
- Keeps the Program Manager's durable task record locally in a Jira-like task
  store, so setup does not require Jira or other third-party credentials.
- Connects the channels that match where the buyer works. For WhatsApp, it
  recommends a separate agent number for a more natural team chat experience,
  while keeping self-chat as an alternative. When there is no preference,
  recommend WhatsApp or Telegram as the quickest route to the employee.

External messages remain drafts until the buyer deliberately authorizes a
specific recipient or channel.
