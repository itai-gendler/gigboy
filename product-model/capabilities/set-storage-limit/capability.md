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

# Set a storage limit

An admin sets how much a person's uploads may take up, or resets it to the default.
