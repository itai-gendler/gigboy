---
kind: primary
routes:
  web: Web
steps:
- text: The User opens Add songs on the setlist and picks songs
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
    - Artist
  - entity: setlist
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::setlist
- text: The Product appends the picked songs that are not already on the setlist
  kind: product
  actor: user
  entities:
  - entity: setlist
    effect: changes
    facts:
    - Songs
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::setlist
references:
- kind: code
  role: implementation
  target: src/context/BandsContext.tsx#addSongsToBandSetlist
---

# Add songs from the library picker

## Trigger

An editor fills a setlist.

## Outcome

The picked songs are at the end of the setlist, each once, and the running time grows.
