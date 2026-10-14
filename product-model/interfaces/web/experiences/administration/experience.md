---
actors:
- admin
access: restricted
entryPoints:
- web: /admin/invites
- web: /admin/users
references:
- kind: code
  role: implementation
  target: src/App.tsx#RequireAdmin
- kind: code
  role: implementation
  target: server/middleware/requireAdmin.ts
---

# Administration

Where admins invite people to the server and manage its users.
