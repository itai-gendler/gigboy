---
appliesTo:
- type: entity
  id: technical-rider
  effect: changes
permits:
- related:
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
  target: server/middleware/bandAccess.ts
- kind: code
  role: implementation
  target: server/routes/bandRiders.ts
- kind: code
  role: implementation
  target: server/routes/bandTrash.ts
---

# Only band editors change technical riders

Editing a technical rider, moving it to the trash and restoring it take an Editor membership in the band.
