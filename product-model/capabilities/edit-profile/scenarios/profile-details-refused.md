---
kind: validation
routes:
  web: Web
steps:
- text: The User enters an email or username another account uses, or an empty full name
  kind: actor
  actor: user
  entities:
  - entity: account
    effect: reads
    facts: []
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
    - Email
    - Username
  contexts:
    web:
      place: web::bands::profile
references:
- kind: code
  role: implementation
  target: server/routes/auth.ts
---

# Taken or invalid details

## Trigger

A user picks details the server does not accept.

## Outcome

The account is unchanged and the profile says what to fix.
