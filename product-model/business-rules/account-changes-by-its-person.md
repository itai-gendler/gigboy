---
appliesTo:
- type: entity
  id: account
  effect: changes
  facts:
  - Email
  - Username
  - Full name
  - Avatar
  - Password
permits:
- related:
  - verb: acts as
    entity: user
references:
- kind: code
  role: implementation
  target: server/routes/auth.ts
---

# Only the person changes their profile and password

Profile details and the password of an account are changed only by the person signed in to it.
