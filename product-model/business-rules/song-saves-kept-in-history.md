---
appliesTo:
- type: capability
  id: add-song
- type: capability
  id: edit-song
- type: capability
  id: change-song-capo
- type: capability
  id: update-song-from-file
- type: capability
  id: restore-song-version
- type: entity
  id: song-version
references:
- kind: code
  role: implementation
  target: server/lib/songRevisions.ts
- kind: code
  role: implementation
  target: server/routes/bandSongs.ts
---

# Every song save is kept in its history

Each save of a song — writing, editing, the capo, updating from a file, restoring a version — is recorded as a version with who made it and what changed; saves by the same person within ten minutes count as one, and a song keeps its latest 100 versions.
