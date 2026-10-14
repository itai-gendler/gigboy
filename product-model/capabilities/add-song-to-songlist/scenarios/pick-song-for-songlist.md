---
kind: primary
routes:
  web: Web
steps:
- text: The User picks a library song from the songlist
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
    - Artist
  - entity: songlist
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::songlist
- text: The Product appends the song to the songlist unless it is already there
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
      place: web::bands::songlist
references:
- kind: code
  role: implementation
  target: src/context/BandsContext.tsx
---

# Add a song from the songlist

## Trigger

An editor files a song in a songlist.

## Outcome

The song is listed in the songlist once.
