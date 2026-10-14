---
appliesTo:
- type: entity
  id: account-invite
  effect: changes
  to: Accepted
permits:
- actors:
  - visitor
references:
- kind: code
  role: implementation
  target: server/routes/invites.ts#publicInvitesRouter
---

# Whoever holds a pending account invite may accept it

An account invite is accepted by the person who opens its link while signed out; no sign-in is needed.
