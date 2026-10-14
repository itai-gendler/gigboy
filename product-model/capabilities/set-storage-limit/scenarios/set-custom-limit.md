---
kind: primary
routes:
  web: Web
steps:
- text: The Admin enters a new limit for a person
  kind: actor
  actor: admin
  entities:
  - entity: account
    effect: reads
    facts:
    - Username
    - Storage limit
  contexts:
    web:
      place: web::administration::users
- text: The Product saves the limit
  kind: product
  actor: admin
  entities:
  - entity: account
    effect: changes
    facts:
    - Storage limit
  contexts:
    web:
      place: web::administration::users
references:
- kind: code
  role: implementation
  target: server/routes/adminUsers.ts
---

# Set a custom limit

## Trigger

A band needs more room, or should use less.

## Outcome

The person's limit is the new value.
