---
kind: primary
routes:
  web: Web
steps:
- text: The User changes their full name, username or email on their profile
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::profile
- text: The Product saves the change to the account
  kind: product
  actor: user
  entities:
  - entity: account
    effect: changes
    facts:
    - Full name
    - Username
    - Email
  contexts:
    web:
      place: web::bands::profile
references:
- kind: code
  role: implementation
  target: server/routes/auth.ts
---

# Change name, username or email

## Trigger

A user wants bandmates to see a different name, or signs in with a new email.

## Outcome

The account shows the new details everywhere bandmates see them.
