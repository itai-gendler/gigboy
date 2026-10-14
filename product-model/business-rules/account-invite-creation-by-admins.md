---
appliesTo:
- type: entity
  id: account-invite
  effect: creates
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: server/routes/invites.ts#adminInvitesRouter
---

# Only admins create account invites

Account invites are issued from the administration pages only.
