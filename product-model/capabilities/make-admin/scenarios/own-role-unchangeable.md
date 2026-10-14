---
kind: validation
routes:
  web: Web
steps:
- text: The Admin tries to change their own role
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::users
- text: The Product refuses and asks them to ask another admin
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

# Own role refused

## Trigger

An admin targets their own account.

## Outcome

Nothing changes; the page says to ask another admin.
