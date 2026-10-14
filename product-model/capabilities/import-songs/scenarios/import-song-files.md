---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses song files or a ZIP backup to import
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::library
- text: The Product converts each file to ChordPro and adds every converted song to the library
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
    - Capo
    - Tempo
    - Time signature
  contexts:
    web:
      place: web::bands::library
- text: The Product reports how many songs were imported and which files failed
  kind: product
  actor: user
  entities:
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::library
references:
- kind: code
  role: implementation
  target: src/utils/songImport.ts
- kind: code
  role: implementation
  target: src/utils/parseSongFile.ts
---

# Import song files or a ZIP backup

## Trigger

An editor moves songs in from another app or a backup.

## Outcome

Every file that could be read is a song in the library; files that could not are named, and the rest still import.
