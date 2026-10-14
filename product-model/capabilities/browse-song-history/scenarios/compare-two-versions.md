---
kind: primary
routes:
  web: Web
steps:
- text: The User opens History on the song
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
- text: The Product lists the saved versions, newest first, with who saved each and what changed
  kind: product
  actor: user
  entities:
  - entity: song-version
    effect: reads
    facts:
    - Saved
    - Saved by
    - Changes
  contexts:
    web:
      place: web::bands::song
- text: The User picks two versions
  kind: actor
  actor: user
  entities:
  - entity: song-version
    effect: reads
    facts:
    - Saved
  contexts:
    web:
      place: web::bands::song
- text: The Product shows the differences line by line
  kind: product
  actor: user
  entities:
  - entity: song-version
    effect: reads
    facts:
    - Song details
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: src/components/SongHistoryPanel.tsx
- kind: code
  role: implementation
  target: src/utils/textDiff.ts
---

# See and compare versions

## Trigger

A member wonders who changed a line.

## Outcome

The member sees what changed between the two versions and by whom.
