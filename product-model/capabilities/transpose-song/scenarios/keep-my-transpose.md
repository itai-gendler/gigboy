---
kind: primary
routes:
  web: Web
steps:
- text: The User presses the key arrows on the song
  kind: actor
  actor: user
  entities:
  - entity: personal-transpose
    effect: reads
    facts:
    - Semitones
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song
- text: The Product shifts every chord and saves the shift as the User's own for this song
  kind: product
  actor: user
  entities:
  - entity: personal-transpose
    effect: creates
    facts:
    - Semitones
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: src/hooks/useSongTranspose.ts
- kind: code
  role: implementation
  target: server/routes/songMemberPrefs.ts
---

# Transpose and keep it

## Trigger

A member reads the song in another key, such as a horn player reading in E-flat.

## Outcome

The song opens in that key for this member next time, here and in concert mode; bandmates' charts are untouched.
