---
availability:
- place: web::administration
domain: account-invites
references:
- kind: code
  role: implementation
  target: server/routes/invites.ts
- kind: code
  role: implementation
  target: src/pages/AdminInvitesPage.tsx
---

# Revoke an account invite

An admin withdraws a pending account invite so its link no longer works.
