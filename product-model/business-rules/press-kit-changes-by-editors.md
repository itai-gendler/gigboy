---
appliesTo:
- type: entity
  id: press-kit
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
  target: server/routes/bandPressKits.ts
- kind: code
  role: implementation
  target: server/routes/bandTrash.ts
---

# Only band editors change press kits

Editing a press kit, moving it to the trash and restoring it take an Editor membership in the band.
