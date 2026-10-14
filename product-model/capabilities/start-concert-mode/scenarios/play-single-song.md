---
kind: alternative
routes:
  web: Web
steps:
- text: The User presses Concert on a song
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song
- text: The Product shows that song alone in concert mode, in the User's own transpose
  kind: product
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
    - Artist
    - Capo
    - Chart
  - entity: personal-transpose
    effect: reads
    facts:
    - Semitones
  contexts:
    web:
      place: web::bands::concert-mode
references:
- kind: code
  role: implementation
  target: src/pages/SongConcertPage.tsx
---

# Play a single song

## Trigger

A member rehearses one song on stage settings.

## Outcome

The song plays in concert mode, without Solo, Follow or Lead.
