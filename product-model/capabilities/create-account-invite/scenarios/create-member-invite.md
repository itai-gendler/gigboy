---
kind: primary
routes:
  web: Web
steps:
- text: The Admin optionally enters an email and picks Member or Admin
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::administration::account-invites
- text: The Product creates a pending invite that expires in seven days and shows its link
  kind: product
  actor: admin
  entities:
  - entity: account-invite
    effect: creates
    to: Pending
    facts:
    - Link
    - Email
    - Role
    - Expires
  contexts:
    web:
      place: web::administration::account-invites
- text: The Admin copies the link to send to the person
  kind: actor
  actor: admin
  entities:
  - entity: account-invite
    effect: reads
    facts:
    - Link
  contexts:
    web:
      place: web::administration::account-invites
references:
- kind: code
  role: implementation
  target: server/routes/invites.ts
---

# Create an invite link

## Trigger

An admin wants to bring someone onto the server.

## Outcome

A pending invite is listed with its role and expiry, and its link can be shared.
