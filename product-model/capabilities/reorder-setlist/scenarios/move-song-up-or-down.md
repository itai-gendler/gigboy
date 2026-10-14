---
kind: primary
routes:
  web: Web
steps:
- text: The User turns on Reorder songs and moves a song up or down
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::bands::setlist
- text: The Product saves the new playing order
  kind: product
  actor: user
  entities:
  - entity: setlist
    effect: changes
    facts:
    - Songs
  contexts:
    web:
      place: web::bands::setlist
references:
- kind: code
  role: implementation
  target: src/context/BandsContext.tsx#moveSongInBandSetlist
---

# Move songs up or down

## Trigger

The band changes the running order.

## Outcome

The setlist plays in the new order, in print and in concert mode.
