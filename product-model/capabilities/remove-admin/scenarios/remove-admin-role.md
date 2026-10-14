---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Remove admin on another admin
  kind: actor
  actor: admin
  entities:
  - entity: account
    effect: reads
    facts:
    - Username
  contexts:
    web:
      place: web::administration::users
- text: The Product makes that person a regular member again
  kind: product
  actor: admin
  entities:
  - entity: admin
    effect: removes
  contexts:
    web:
      place: web::administration::users
references:
- kind: code
  role: implementation
  target: server/routes/adminUsers.ts
---

# Remove an admin

## Trigger

Someone no longer helps run the server.

## Outcome

The person keeps their account and bands but loses the administration pages.
