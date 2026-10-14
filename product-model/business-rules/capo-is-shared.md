---
appliesTo:
- type: capability
  id: change-song-capo
  contexts:
  - place: web::bands
references:
- kind: code
  role: implementation
  target: src/components/SongView.tsx
---

# The capo is shared by the whole band

Changing the capo on the song page changes the song itself for every member, unlike the transpose.
