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

# Delete user

An admin deletes another user and every band that user owns.
