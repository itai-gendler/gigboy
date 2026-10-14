---
kind: validation
routes:
  web: Web
steps:
- text: The User opens concert mode on a setlist with no songs
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts: []
  - entity: setlist
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::setlist
- text: The setlist has no songs
  kind: condition
  entities:
  - entity: setlist
    effect: reads
    facts:
    - Songs
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::concert-mode
- text: The Product says the setlist has no songs yet and offers the way back
  kind: product
  actor: user
  entities:
  - entity: song
    effect: reads
    facts: []
  - entity: setlist
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::concert-mode
references:
- kind: code
  role: implementation
  target: src/pages/BandSetlistConcertPage.tsx
---

# Empty setlist

## Trigger

A member starts concert mode too early.

## Outcome

Nothing plays until songs are added.
