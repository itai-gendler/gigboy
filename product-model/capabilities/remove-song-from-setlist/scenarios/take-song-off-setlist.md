---
kind: primary
routes:
  web: Web
steps:
- text: The User presses the bin on a song row of the setlist
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
  - entity: setlist
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::setlist
- text: The Product takes the song and its stage note off the setlist
  kind: product
  actor: user
  entities:
  - entity: setlist
    effect: changes
    facts:
    - Songs
    - Stage notes
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::setlist
references:
- kind: code
  role: implementation
  target: src/context/BandsContext.tsx#removeSongFromBandSetlist
---

# Remove a song from a setlist

## Trigger

A song is cut from the set.

## Outcome

The setlist no longer has the song or its note; the library still has the song.
