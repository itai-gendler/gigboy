---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor enters a password under 8 characters, a username under 2, or an email or username already in use
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::public::join-gigboy
- text: The Product refuses the details and keeps the invite pending
  kind: product
  actor: visitor
  entities:
  - entity: account
    effect: reads
    facts:
    - Email
    - Username
  contexts:
    web:
      place: web::public::join-gigboy
references:
- kind: code
  role: implementation
  target: server/routes/invites.ts
---

# Invalid or taken account details

## Trigger

An invitee submits details the server does not accept.

## Outcome

No account is created, the invite stays usable, and the page names what to fix.
