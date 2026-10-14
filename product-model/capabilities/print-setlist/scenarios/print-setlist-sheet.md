---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the print view of the setlist
  kind: actor
  actor: user
  entities:
  - entity: setlist
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::setlist
- text: The Product lays out one large-type page with the song order, key, BPM and stage notes
  kind: product
  actor: user
  entities:
  - entity: setlist
    effect: reads
    facts:
    - Name
    - Songs
    - Stage notes
  - entity: song
    effect: reads
    facts:
    - Title
    - Artist
    - Key
    - Tempo
  contexts:
    web:
      place: web::bands::setlist-print
- text: The User prints it or saves it as PDF
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::setlist-print
references:
- kind: code
  role: implementation
  target: src/pages/BandSetlistPrintPage.tsx
---

# Print the setlist sheet

## Trigger

The band wants a sheet to tape to the stage floor.

## Outcome

The printed sheet lists the set in order with keys, tempos and notes.
