---
kind: primary
routes:
  web: Web
steps:
- text: The User picks a song in the library
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::bands::library
- text: The Product shows the chart with chords above the lyrics, shifted by the User's personal transpose when they have one
  kind: product
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
    - Artist
    - Author
    - Chart
    - Key
    - Capo
    - Tempo
    - Time signature
    - Duration
    - Playback link
  - entity: personal-transpose
    effect: reads
    facts:
    - Semitones
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: src/components/SongView.tsx
- kind: code
  role: implementation
  target: src/hooks/useSongTranspose.ts
---

# Read a song

## Trigger

A member wants to read or rehearse a song.

## Outcome

The song page shows the chart in the key the member last chose for it, with the shared capo.
