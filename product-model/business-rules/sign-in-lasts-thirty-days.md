---
appliesTo:
- type: capability
  id: sign-in
  contexts:
  - place: web::public
references:
- kind: code
  role: implementation
  target: server/middleware/session.ts
---

# A sign-in lasts 30 days

A device stays signed in for 30 days after signing in, unless it signs out or the password changes elsewhere.
