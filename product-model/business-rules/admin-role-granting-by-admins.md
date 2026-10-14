---
appliesTo:
- type: entity
  id: admin
  effect: creates
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: server/routes/adminUsers.ts
---

# Only admins make someone an admin

Outside an admin invite, only an admin gives another person the Admin role.
