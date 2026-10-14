---
appliesTo:
- type: capability
  id: write-song-notes
- type: capability
  id: delete-song-notes
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#handNotes
---

# Each member keeps one set of notes per song

A member's drawing and typed notes on a song are one set, which only they add to.
