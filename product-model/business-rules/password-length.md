---
appliesTo:
- type: capability
  id: accept-account-invite
- type: capability
  id: change-password
references:
- kind: code
  role: implementation
  target: server/routes/invites.ts
- kind: code
  role: implementation
  target: server/routes/auth.ts
---

# Passwords have at least eight characters

A password shorter than eight characters is refused when creating an account or changing a password.
