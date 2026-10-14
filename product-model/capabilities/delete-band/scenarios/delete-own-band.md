---
kind: primary
routes:
  web: Web
steps:
- text: The User types the band name to confirm, under Danger zone in band settings
  kind: actor
  actor: user
  entities:
  - entity: band
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::band-settings
- text: The Product deletes the band with its memberships and everything it keeps
  kind: product
  actor: user
  entities:
  - entity: band
    effect: removes
  - entity: membership
    effect: removes
    with: band
  contexts:
    web:
      place: web::bands::band-settings
references:
- kind: code
  role: implementation
  target: server/routes/bands.ts
---

# Delete the band

## Trigger

The owner ends the band in Gigboy.

## Outcome

The band, its members' access and all its songs, lists, gigs, tours and trash are gone.
