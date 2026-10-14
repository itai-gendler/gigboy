---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Download on the song
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
- text: The Product saves a ChordPro file with the title, artist, author, key, capo, tempo and time signature above the chart
  kind: product
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
    - Artist
    - Author
    - Key
    - Capo
    - Tempo
    - Time signature
    - Chart
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: src/components/SongView.tsx
---

# Download as ChordPro

## Trigger

A member wants the song outside Gigboy.

## Outcome

The member has a file any ChordPro app opens.
