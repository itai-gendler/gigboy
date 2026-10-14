---
kind: alternative
routes:
  web: Web
steps:
- text: The User picks Full charts in the print view
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::setlist-print
- text: The Product lays out every song chart one song per page, with its stage note
  kind: product
  actor: user
  entities:
  - entity: setlist
    effect: reads
    facts:
    - Songs
    - Stage notes
  - entity: song
    effect: reads
    facts:
    - Title
    - Artist
    - Chart
  contexts:
    web:
      place: web::bands::setlist-print
references:
- kind: code
  role: implementation
  target: src/pages/BandSetlistPrintPage.tsx
---

# Print the full charts

## Trigger

A member wants paper charts for the gig.

## Outcome

Each song of the set prints on its own page.
