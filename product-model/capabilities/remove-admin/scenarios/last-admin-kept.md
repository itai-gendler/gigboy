---
kind: validation
routes:
  web: Web
steps:
- text: The Admin tries to remove the Admin role from the only other admin left
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::users
- text: No other admin would remain
  kind: condition
  entities:
  - entity: admin
    effect: reads
    facts: []
  contexts:
    web:
      place: web::administration::users
- text: The Product refuses because at least one admin must remain
  kind: product
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::users
references:
- kind: code
  role: implementation
  target: server/routes/adminUsers.ts
---

# Last admin kept

## Trigger

A demotion would leave the server without an admin.

## Outcome

The role is unchanged and the page says at least one admin must remain.
