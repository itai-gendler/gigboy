---
entities:
- entity: account
  shows:
  - Email
  - Username
  - Full name
  - Storage limit
  collects:
  - Storage limit
- admin
entryPoints:
- web: /admin/users
references:
- kind: code
  role: implementation
  target: src/pages/AdminUsersPage.tsx
---

# Users

Every account on the server, who is an admin, how much storage the bands they own use, their storage limit, and the controls to change that or delete a user.
