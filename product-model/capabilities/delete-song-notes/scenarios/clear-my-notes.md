---
kind: primary
routes:
  web: Web
steps:
- text: The User clears their notes on the song
  kind: actor
  actor: user
  entities:
  - entity: song-note
    effect: reads
    facts:
    - Drawing
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song
- text: The Product deletes the User's notes on this song
  kind: product
  actor: user
  entities:
  - entity: song-note
    effect: removes
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/songHandNotes.ts
---

# Clear my notes

## Trigger

A member starts over.

## Outcome

The member has no notes on the song.
