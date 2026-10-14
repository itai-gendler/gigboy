---
kind: validation
routes:
  web: Web
steps:
- text: The User enters a wrong current password
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::profile
- text: The Product refuses the change
  kind: product
  actor: user
  entities:
  - entity: account
    effect: reads
    facts:
    - Password
  contexts:
    web:
      place: web::bands::profile
references:
- kind: code
  role: implementation
  target: server/routes/auth.ts
---

# Wrong current password

## Trigger

A user mistypes their current password.

## Outcome

The password is unchanged and the profile says the current password is incorrect.
