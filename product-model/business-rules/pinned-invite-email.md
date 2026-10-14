---
appliesTo:
- type: capability
  id: accept-account-invite
  contexts:
  - place: web::public
- type: capability-scenario
  id: create-member-invite
references:
- kind: code
  role: implementation
  target: server/routes/invites.ts
---

# An invite's pinned email becomes the account email

When an admin pins an email to an account invite, the new account gets that email whatever the invitee enters.
