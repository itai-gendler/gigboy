---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Update from file on the song, picks a file and confirms
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::bands::song
- text: The Product converts the file and replaces the chart, keeping any detail the file does not carry
  kind: product
  actor: user
  entities:
  - entity: song
    effect: changes
    facts:
    - Title
    - Artist
    - Author
    - Language
    - Other languages
    - Tags
    - Chart
    - Key
    - Capo
    - Tempo
    - Time signature
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: src/components/SongView.tsx
---

# Replace the chart from a file

## Trigger

A member has a newer version of the chart in another app.

## Outcome

The song shows the file's chart; the previous one stays in its history.
