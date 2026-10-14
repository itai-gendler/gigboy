---
kind: alternative
routes:
  web: Web
steps:
- text: The User draws or types more on a song they already marked
  kind: actor
  actor: user
  entities:
  - entity: song-note
    effect: reads
    facts:
    - Drawing
    - Typed notes
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song
- text: The Product saves the User's updated notes
  kind: product
  actor: user
  entities:
  - entity: song-note
    effect: changes
    facts:
    - Drawing
    - Typed notes
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/songHandNotes.ts
---

# Add to existing notes

## Trigger

A member keeps marking the sheet.

## Outcome

The member's notes include the new marks.
