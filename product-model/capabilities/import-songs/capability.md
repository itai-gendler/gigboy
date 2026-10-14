---
availability:
- place: web::bands
domain: library
references:
- kind: code
  role: implementation
  target: src/pages/BandDetailPage.tsx
- kind: code
  role: implementation
  target: src/utils/songImport.ts
---

# Import songs

An editor imports song files or a ZIP backup — ChordPro, OnSong or pasted charts — and Gigboy converts each into a ChordPro song.
