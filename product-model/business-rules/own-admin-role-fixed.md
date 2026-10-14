---
appliesTo:
- type: capability
  id: make-admin
- type: capability
  id: remove-admin
references:
- kind: code
  role: implementation
  target: server/routes/adminUsers.ts
---

# An admin's own role is changed by another admin

Admins cannot make or remove themselves as admin.
