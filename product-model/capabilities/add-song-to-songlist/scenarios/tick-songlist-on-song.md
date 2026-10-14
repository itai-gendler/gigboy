---
kind: alternative
routes:
  web: Web
steps:
- text: The User opens Add to on a song and ticks a songlist
  kind: actor
  actor: user
  entities:
  - entity: songlist
    effect: reads
    facts:
    - Name
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song
- text: The Product appends the song to that songlist
  kind: product
  actor: user
  entities:
  - entity: songlist
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

# Tick a songlist from the song

## Trigger

An editor files the song they are looking at.

## Outcome

The song is in the ticked songlist.
