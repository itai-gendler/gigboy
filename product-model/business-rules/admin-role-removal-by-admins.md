---
appliesTo:
- type: entity
  id: admin
  effect: removes
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: server/routes/adminUsers.ts
---

# Only admins remove an admin

Only an admin takes the Admin role away from another admin.
