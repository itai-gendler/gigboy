---
appliesTo:
- type: entity
  id: account-invite
  effect: changes
  to: Revoked
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: server/routes/invites.ts#adminInvitesRouter
---

# Only admins revoke account invites

Revoking a pending account invite is for admins.
