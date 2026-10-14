---
appliesTo:
- type: entity
  id: song-note
  effect: changes
permits:
- related:
  - verb: writes
    entity: user
references:
- kind: code
  role: implementation
  target: server/routes/songHandNotes.ts
---

# Only its author changes a member's song notes

Each member draws and types only their own notes on a song.
