---
kind: alternative
routes:
  web: Web
steps:
- text: The User opens Add to on a song and ticks a setlist
  kind: actor
  actor: user
  entities:
  - entity: setlist
    effect: reads
    facts:
    - Name
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song
- text: The Product appends the song to that setlist
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
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: src/components/AddToMenu.tsx
---

# Tick a setlist from the song

## Trigger

An editor adds the song they are looking at.

## Outcome

The song is the last one on the ticked setlist.
