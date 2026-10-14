---
kind: primary
routes:
  web: Web
steps:
- text: The User removes a song row from the songlist
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
  - entity: songlist
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::songlist
- text: The Product takes the song off the songlist
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

# Remove a song from a songlist

## Trigger

A song no longer belongs in a songlist.

## Outcome

The songlist no longer lists the song; the library still has it.
