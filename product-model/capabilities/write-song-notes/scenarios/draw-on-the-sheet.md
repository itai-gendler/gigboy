---
kind: primary
routes:
  web: Web
steps:
- text: The User ticks Draw or Type and marks the sheet
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Chart
  contexts:
    web:
      place: web::bands::song
- text: The Product saves the marks as the User's own notes on this song
  kind: product
  actor: user
  entities:
  - entity: song-note
    effect: creates
    facts:
    - Drawing
    - Typed notes
    - Author
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

# Draw or type on the sheet

## Trigger

A member wants a reminder a text note cannot capture, such as a circled bar.

## Outcome

The notes stay on the sheet for this member.
