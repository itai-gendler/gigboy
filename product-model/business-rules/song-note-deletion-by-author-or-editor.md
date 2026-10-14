---
appliesTo:
- type: entity
  id: song-note
  effect: removes
permits:
- related:
  - verb: writes
    entity: user
- related:
  - verb: has
    entity: song
  - verb: keeps
    entity: band
  - verb: has
    entity: membership
  - verb: holds
    entity: user
  when:
  - entity: membership
    fact: Role
    is: Editor
references:
- kind: code
  role: implementation
  target: server/routes/songHandNotes.ts
---

# Only its author, or an editor, deletes a member's song notes

A member clears their own notes; a band editor may also delete a bandmate's.
