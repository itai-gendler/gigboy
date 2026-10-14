---
kind: alternative
routes:
  web: Web
steps:
- text: The User fills in a new song and picks a songlist under Save to song list
  kind: actor
  actor: user
  entities:
  - entity: songlist
    effect: reads
    facts:
    - Name
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song-editor
- text: The Product saves the song to the library and adds it to that songlist
  kind: product
  actor: user
  entities:
  - entity: song
    effect: creates
    to: Active
    facts:
    - Title
    - Artist
    - Author
    - Language
    - Other languages
    - Tags
    - Chart
    - Key
    - Tempo
    - Time signature
    - Date
    - Duration
    - Playback link
  - entity: songlist
    effect: changes
    facts:
    - Songs
  contexts:
    web:
      place: web::bands::song-editor
references:
- kind: code
  role: implementation
  target: src/pages/AddSongPage.tsx
---

# Add a song straight into a songlist

## Trigger

An editor adds a song while filing it.

## Outcome

The song is in the library and in the chosen songlist.
