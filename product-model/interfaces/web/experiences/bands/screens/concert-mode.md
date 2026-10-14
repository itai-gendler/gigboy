---
entities:
- entity: song
  shows:
  - Title
  - Artist
  - Capo
  - Chart
  - Tempo
- entity: setlist
  shows:
  - Name
  - Songs
  - Stage notes
- entity: setlist-session
  shows:
  - Song position
  - Page position
  - Transpose
- entity: account
  shows:
  - Full name
  - Username
  - Avatar
entryPoints:
- web: /bands/:bandId/setlists/:setlistId/concert
- web: /songs/:id/concert
references:
- kind: code
  role: implementation
  target: src/components/ConcertModeView.tsx
- kind: code
  role: implementation
  target: src/pages/BandSetlistConcertPage.tsx
---

# Concert mode

The on-stage view: one song at a time, paged or scrolling, played from a setlist or a single song, with Solo, Follow and Lead for playing a setlist together.
