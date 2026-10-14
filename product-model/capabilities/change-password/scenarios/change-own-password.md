---
kind: primary
routes:
  web: Web
steps:
- text: The User enters their current password and a new one of at least 8 characters
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::profile
- text: The Product checks the current password and saves the new one
  kind: product
  actor: user
  entities:
  - entity: account
    effect: changes
    facts:
    - Password
  contexts:
    web:
      place: web::bands::profile
- text: The Product signs out every other device of the account
  kind: product
  actor: user
  entities:
  - entity: account
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::profile
references:
- kind: code
  role: implementation
  target: server/routes/auth.ts
- kind: code
  role: implementation
  target: server/middleware/session.ts#revokeOtherSessions
---

# Change password

## Trigger

A user wants a new password.

## Outcome

The new password works, this device stays signed in and every other device must sign in again.
