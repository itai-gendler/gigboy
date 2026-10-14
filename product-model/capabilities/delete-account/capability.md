---
availability:
- place: web::bands
domain: profile
references:
- kind: code
  role: implementation
  target: server/routes/auth.ts
- kind: code
  role: implementation
  target: src/pages/ProfilePage.tsx
---

# Delete account

A user permanently deletes their own account, and with it every band they own.
