---
entities:
- entity: songlist
  shows:
  - Name
  - Songs
  collects:
  - Name
- entity: song
  shows:
  - Title
  - Artist
entryPoints:
- web: /bands/:id/songlists/:songListId
references:
- kind: code
  role: implementation
  target: src/pages/BandDetailPage.tsx
---

# Songlist

One songlist and its songs.
