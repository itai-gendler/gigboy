---
appliesTo:
- type: capability
  id: remove-admin
- type: capability
  id: delete-user
references:
- kind: code
  role: implementation
  target: server/routes/adminUsers.ts
---

# At least one admin always remains

Removing the Admin role is refused when no other admin would be left, and an admin cannot delete themselves from the Users page.
