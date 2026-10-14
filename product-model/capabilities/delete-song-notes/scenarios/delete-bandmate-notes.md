---
kind: alternative
routes:
  web: Web
steps:
- text: The User deletes a bandmate's notes and confirms
  kind: actor
  actor: user
  entities:
  - entity: song-note
    effect: reads
    facts:
    - Author
  contexts:
    web:
      place: web::bands::song
- text: The Product deletes that bandmate's notes on this song
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

# Delete a bandmate's notes

## Trigger

An editor tidies up a song's sheet.

## Outcome

The bandmate's notes are gone for everyone.
