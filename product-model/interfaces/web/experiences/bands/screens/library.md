---
entities:
- entity: band
  shows:
  - Name
- entity: song
  shows:
  - Title
  - Artist
  - Language
  - Key
  - Tempo
  - Date
  - Duration
  - Tags
entryPoints:
- web: /bands/:id/library
references:
- kind: code
  role: implementation
  target: src/pages/BandDetailPage.tsx
- kind: code
  role: implementation
  target: src/components/SongList.tsx
---

# Library

Every song the band keeps, with search, sort and filters.
