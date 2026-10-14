---
kind: primary
routes:
  web: Web
steps:
- text: The User switches on a bandmate's notes
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
- text: The Product shows that bandmate's drawing and typed notes on the sheet
  kind: product
  actor: user
  entities:
  - entity: song-note
    effect: reads
    facts:
    - Drawing
    - Typed notes
    - Author
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: src/hooks/useSongHandNotes.ts
---

# Show one bandmate's notes

## Trigger

A member wants to see what the drummer marked.

## Outcome

The bandmate's notes show beside the member's own until switched off.
