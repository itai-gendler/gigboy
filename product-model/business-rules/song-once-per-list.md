---
appliesTo:
- type: capability
  id: add-songs-to-setlist
- type: capability
  id: add-song-to-songlist
references:
- kind: code
  role: implementation
  target: src/context/BandsContext.tsx#addSongsToBandSetlist
---

# A song appears at most once in a setlist or songlist

Adding a song that is already on the list leaves the list as it was.
