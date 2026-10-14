---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Log out on their profile
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::profile
- text: The Product ends the sign-in on this device
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::profile
references:
- kind: code
  role: implementation
  target: server/routes/auth.ts
---

# Sign out

## Trigger

A user wants to leave Gigboy on this device.

## Outcome

This device is signed out; other devices stay signed in.
