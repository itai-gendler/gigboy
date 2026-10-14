---
appliesTo:
- type: entity
  id: recording-comment
  effect: removes
permits:
- related:
  - verb: writes
    entity: user
- related:
  - verb: has
    entity: recording
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
  target: server/routes/recordingComments.ts
---

# Only its author, or an editor, deletes a recording comment

A comment on a take is deleted by the member who wrote it or by a band editor.
