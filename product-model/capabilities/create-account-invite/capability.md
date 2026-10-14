---
availability:
- place: web::administration
domain: account-invites
references:
- kind: code
  role: implementation
  target: server/routes/invites.ts#adminInvitesRouter
- kind: code
  role: implementation
  target: src/pages/AdminInvitesPage.tsx
---

# Create an account invite

An admin creates an account invite link, optionally pinned to an email, for a member or an admin.
