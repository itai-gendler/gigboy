---
entities:
- entity: account-invite
  shows:
  - Link
  - Email
  - Role
  - Expires
  collects:
  - Email
  - Role
entryPoints:
- web: /admin/invites
references:
- kind: code
  role: implementation
  target: src/pages/AdminInvitesPage.tsx
---

# Invites

Where admins create account invites and see and revoke the pending ones.
