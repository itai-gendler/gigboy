---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the band invite link and accepts the invite
  kind: actor
  actor: user
  entities:
  - entity: band-invite
    effect: reads
    facts:
    - Role
  contexts:
    web:
      place: web::bands::join-band
- text: The Product checks the link has not expired
  kind: condition
  entities:
  - entity: band-invite
    effect: reads
    facts:
    - Expires
  contexts:
    web:
      place: web::bands::join-band
- text: The Product adds the User to the band as an editor
  kind: product
  actor: user
  entities:
  - entity: membership
    effect: creates
    facts:
    - Role
    - Joined
  - entity: band
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::join-band
- text: The Product opens the band's library
  kind: product
  actor: user
  entities:
  - entity: band
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::library
references:
- kind: code
  role: implementation
  target: server/routes/bands.ts
---

# Join from an invite link

## Trigger

A bandmate sent the user a band invite link.

## Outcome

The user is an editor of the band and is in its library.

## Edge cases

- Joining a band the user already belongs to changes nothing and still opens its library.
- Choosing Not now joins nothing and returns the user to their bands.
