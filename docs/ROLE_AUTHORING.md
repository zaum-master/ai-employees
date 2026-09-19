# Adding an AI employee role

Each role is a separate folder under `roles/`. To add a role such as Supply
Manager:

1. Create `roles/<role-id>/` with `ROLE.md`, `INTAKE.md`, `INSTALL.md`, local
   task-store instructions, and generated-file templates.
2. Keep the role's business judgment in its written instructions. Add code only
   for a narrow fetch, send, or duplicate guard with a stated invariant.
3. Add the role to `roles.json` with status `ready` only after its onboarding
   and first-result proof are complete.
4. Update the ready-role table in `README.md`.

Do not merge the role's client-specific data, credentials, contact lists, or
runtime state into this template repository.

