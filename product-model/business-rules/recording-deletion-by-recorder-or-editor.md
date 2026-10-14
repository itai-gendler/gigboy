---
appliesTo:
- type: entity
  id: recording
  effect: removes
permits:
- related:
  - verb: records
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
  target: server/routes/songRecordings.ts
---

# Only the member who recorded a take, or an editor, deletes it

A take is deleted by whoever added it or by a band editor.
