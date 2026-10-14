---
appliesTo:
- type: entity
  id: attachment
  effect: changes
  to: Active
permits:
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
  target: server/routes/bandTrash.ts
---

# Only band editors restore an attachment

Bringing an attachment back from the trash takes an Editor membership in the band.
