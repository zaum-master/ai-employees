# Adding an AI employee role

Each role is a separate folder under `roles/`. To add a role such as Supply
Planning Analyst:

1. Create `roles/<role-id>/ROLE.md` with the role purpose, work loop, human
   approval boundaries, intake facts, and first useful result.
2. Use the shared package under `roles/_shared/` unless the role genuinely
   needs a different runtime contract. The shared package supplies intake,
   installation, task-store, and generated-file templates.
3. Keep the role's business judgment in its written instructions. Add code only
   for a narrow fetch, send, or duplicate guard with a stated invariant.
4. Add the role to `roles.json` with status `ready` only after its onboarding
   and first-result proof are complete.
   Use `preview` while the role has a complete template but lacks that live
   proof.
5. Update the role table in `README.md`.

Do not merge the role's client-specific data, credentials, contact lists, or
runtime state into this template repository.
