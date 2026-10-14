---
kind: primary
routes:
  web: Web
steps:
- text: The User opens Edit on the song and changes its details or chart
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
    - Chart
  contexts:
    web:
      place: web::bands::song
- text: The Product autosaves the song as the User types and keeps the save in its history
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
    - Tempo
    - Time signature
    - Date
    - Duration
    - Playback link
  contexts:
    web:
      place: web::bands::song-editor
references:
- kind: code
  role: implementation
  target: src/components/AddSongForm.tsx
- kind: code
  role: implementation
  target: server/lib/songRevisions.ts
---

# Edit a song

## Trigger

An editor corrects or extends a song.

## Outcome

Every bandmate sees the updated song, and the save shows in its edit history.

## Edge cases

- Saves the same editor makes within ten minutes are kept as one history entry.
- Picking another songlist under Save to song list moves the song from its old songlist to the new one.
