---
kind: alternative
routes:
  web: Web
steps:
- text: The User edits the band name in the library title
  kind: actor
  actor: user
  entities:
  - entity: band
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::library
- text: The Product saves the new name
  kind: product
  actor: user
  entities:
  - entity: band
    effect: changes
    facts:
    - Name
  contexts:
    web:
      place: web::bands::library
references:
- kind: code
  role: implementation
  target: src/pages/BandDetailPage.tsx
- kind: code
  role: implementation
  target: server/routes/bands.ts
---

# Rename the band from the library

## Trigger

An editor fixes the band name while looking at the library.

## Outcome

The band carries the new name.
