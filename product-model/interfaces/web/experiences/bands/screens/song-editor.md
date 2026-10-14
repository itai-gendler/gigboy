---
entities:
- entity: song
  collects:
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
  shows:
  - Name
entryPoints:
- web: /songs/new
- web: /songs/:id/edit
references:
- kind: code
  role: implementation
  target: src/components/AddSongForm.tsx
- kind: code
  role: implementation
  target: src/pages/AddSongPage.tsx
- kind: code
  role: implementation
  target: src/pages/EditSongPage.tsx
---

# Song editor

Where a song is written or edited, with a live preview.
