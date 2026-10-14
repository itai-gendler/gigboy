---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Remove next to a member in band settings
  kind: actor
  actor: user
  entities:
  - entity: account
    effect: reads
    facts:
    - Username
  - entity: band
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::band-settings
- text: The Product removes that membership
  kind: product
  actor: user
  entities:
  - entity: membership
    effect: removes
  contexts:
    web:
      place: web::bands::band-settings
references:
- kind: code
  role: implementation
  target: server/routes/bands.ts
---

# Remove a member

## Trigger

The owner takes someone out of the band.

## Outcome

The person no longer sees the band, and their calendar link for it stops working.

## Edge cases

- The owner has no Remove button for themselves; the band owner cannot be removed.
