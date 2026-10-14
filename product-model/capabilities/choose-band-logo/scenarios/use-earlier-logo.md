---
kind: primary
routes:
  web: Web
steps:
- text: The User picks a logo from the library
  kind: actor
  actor: user
  entities:
  - entity: band-logo
    effect: reads
    facts:
    - Picture
  contexts:
    web:
      place: web::bands::band-settings
- text: The Product makes it the band logo
  kind: product
  actor: user
  entities:
  - entity: band
    effect: changes
    facts:
    - Logo
  - entity: band-logo
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::band-settings
references:
- kind: code
  role: implementation
  target: server/routes/bandLogos.ts
---

# Use an earlier logo

## Trigger

The band goes back to an older logo.

## Outcome

The chosen logo shows everywhere.
