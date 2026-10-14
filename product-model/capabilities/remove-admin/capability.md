---
availability:
- place: web::administration
domain: users
references:
- kind: code
  role: implementation
  target: server/routes/adminUsers.ts
- kind: code
  role: implementation
  target: src/pages/AdminUsersPage.tsx
---

# Remove admin

An admin takes the Admin role away from another admin.
