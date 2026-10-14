---
kind: primary
routes:
  web: Web
steps:
- text: The User presses the capo plus or minus on the song
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Capo
  contexts:
    web:
      place: web::bands::song
- text: The Product saves the new capo fret, from none up to 12, on the song
  kind: product
  actor: user
  entities:
  - entity: song
    effect: changes
    facts:
    - Capo
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: src/components/SongView.tsx
- kind: code
  role: implementation
  target: server/routes/bandSongs.ts
---

# Set the capo

## Trigger

A member plays the song with a capo.

## Outcome

Every bandmate sees the new capo on the song and in concert mode, and the change shows in the song history.
