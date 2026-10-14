---
appliesTo:
- type: capability
  id: change-password
  contexts:
  - place: web::bands
references:
- kind: code
  role: implementation
  target: server/middleware/session.ts#revokeOtherSessions
---

# Changing the password signs out every other device

After a password change only the device that made it stays signed in.
