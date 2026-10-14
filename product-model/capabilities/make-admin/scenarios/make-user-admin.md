---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Make admin on another user
  kind: actor
  actor: admin
  entities:
  - entity: account
    effect: reads
    facts:
    - Username
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::users
- text: The Product gives that user the Admin role
  kind: product
  actor: admin
  entities:
  - entity: admin
    effect: creates
    facts: []
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::users
references:
- kind: code
  role: implementation
  target: server/routes/adminUsers.ts
---

# Make a user an admin

## Trigger

An admin wants another person to help run the server.

## Outcome

The user is listed as an admin and can open the administration pages.
