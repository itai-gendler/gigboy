---
appliesTo:
- type: entity
  id: account
  effect: removes
permits:
- related:
  - verb: acts as
    entity: user
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: server/routes/auth.ts
- kind: code
  role: implementation
  target: server/routes/adminUsers.ts
---

# Only the person or an admin deletes an account

A person deletes their own account from their profile; an admin deletes other people from the Users page.
