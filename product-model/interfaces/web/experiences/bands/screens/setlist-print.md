---
entities:
- entity: setlist
  shows:
  - Name
  - Songs
  - Stage notes
- entity: song
  shows:
  - Title
  - Artist
  - Key
  - Tempo
  - Chart
entryPoints:
- web: /bands/:bandId/setlists/:setlistId/print
references:
- kind: code
  role: implementation
  target: src/pages/BandSetlistPrintPage.tsx
---

# Setlist print view

A setlist laid out for printing or saving as PDF: a large-type setlist sheet, or every full chart one song per page.
