---
entities:
- entity: setlist
  shows:
  - Name
  - Songs
  - Stage notes
  - Running time
  collects:
  - Name
  - Stage notes
- entity: song
  shows:
  - Title
  - Artist
  - Key
  - Tempo
  - Duration
entryPoints:
- web: /bands/:id/setlists/:setlistId
references:
- kind: code
  role: implementation
  target: src/components/SetlistsView.tsx
---

# Setlist

One setlist: its songs in order, their stage notes and the running time.
