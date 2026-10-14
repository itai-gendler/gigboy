---
appliesTo:
- type: capability
  id: accept-account-invite
- type: capability
  id: create-account-invite
references:
- kind: code
  role: implementation
  target: server/routes/invites.ts
---

# An account invite creates one account within seven days

An account invite works once, and only while pending and less than seven days old.
