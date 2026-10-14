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
  target: server/routes/songMemberPrefs.ts
---

# Transpose a song

A member shifts every chord of a song up or down by semitones; the choice sticks to the song for that member only.
