---
kind: validation
routes:
  web: Web
steps:
- text: The User accepts an invite created more than seven days ago
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::join-band
- text: The link has expired
  kind: condition
  entities:
  - entity: band-invite
    effect: reads
    facts:
    - Expires
  contexts:
    web:
      place: web::bands::join-band
- text: The Product says the invite has expired
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::join-band
references:
- kind: code
  role: implementation
  target: server/routes/bands.ts
---

# Expired invite link

## Trigger

A bandmate opens an old invite link.

## Outcome

The user does not join; a band editor needs to create a new link.
