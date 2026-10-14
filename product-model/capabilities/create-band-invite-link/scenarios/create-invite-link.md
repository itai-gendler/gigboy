---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Create invite link
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::band-members
- text: The Product creates a link that grants the Editor role and works for seven days
  kind: product
  actor: user
  entities:
  - entity: band-invite
    effect: creates
    facts:
    - Link
    - Role
    - Expires
  contexts:
    web:
      place: web::bands::band-members
- text: The User copies or shares the link
  kind: actor
  actor: user
  entities:
  - entity: band-invite
    effect: reads
    facts:
    - Link
  contexts:
    web:
      place: web::bands::band-members
references:
- kind: code
  role: implementation
  target: server/routes/bands.ts
---

# Create and share an invite link

## Trigger

An editor wants bandmates to join.

## Outcome

The link can be shared with the bandmates who should join, until it expires.
