---
availability:
- place: web::bands
domain: library
references:
- kind: code
  role: implementation
  target: src/components/SongView.tsx
- kind: code
  role: implementation
  target: src/utils/parseSongFile.ts
---

# Update a song from a file

An editor replaces a song's chart, and the details the file carries, with a ChordPro, OnSong or chart file.
