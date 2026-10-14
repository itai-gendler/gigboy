---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Restore on an earlier version and confirms
  kind: actor
  actor: user
  entities:
  - entity: song-version
    effect: reads
    facts:
    - Saved
    - Saved by
  contexts:
    web:
      place: web::bands::song
- text: The Product puts the song's details and chart back as they were in that version
  kind: product
  actor: user
  entities:
  - entity: song-version
    effect: reads
    facts:
    - Song details
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
    - Date
    - Duration
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/songRevisions.ts
---

# Restore an earlier version

## Trigger

A change made the song worse.

## Outcome

The song is as it was; the restore itself shows as the newest version.
