---
kind: primary
routes:
  web: Web
steps:
- text: The User presses the add button in the library
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::library
- text: The User fills in the title, details and the ChordPro chart
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::song-editor
- text: The Product saves the song to the library and keeps the save in its history
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
  contexts:
    web:
      place: web::bands::song-editor
- text: The Product opens the new song
  kind: product
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
references:
- kind: code
  role: implementation
  target: src/components/AddSongForm.tsx
- kind: code
  role: implementation
  target: server/routes/bandSongs.ts
---

# Write a new song

## Trigger

An editor has a song to add.

## Outcome

The song is in the library and the editor is on its song page.

## Edge cases

- A pasted Ultimate Guitar, Chordify or CifraClub chart, or solfège chords, are converted to ChordPro in the editor.
- A playback link that is not a YouTube or Spotify link is refused before saving.
