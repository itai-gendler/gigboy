---
appliesTo:
- type: entity
  id: song
  effect: removes
permits:
- related:
  - verb: keeps
    entity: band
  - verb: owns
    entity: user
- unattended: true
references:
- kind: code
  role: implementation
  target: server/routes/bandTrash.ts
- kind: code
  role: implementation
  target: server/lib/trash.ts#sweepExpiredBandTrash
---

# Only the band owner deletes trashed songs for good

Deleting a song from the trash for good, one item or by emptying the trash, is for the band owner; the Product itself deletes it once it has been in the trash for 30 days.
