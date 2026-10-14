---
appliesTo:
- type: entity
  id: attachment
  effect: removes
permits:
- related:
  - verb: has
    entity: song
  - verb: keeps
    entity: band
  - verb: owns
    entity: user
- unattended: true
references:
- kind: code
  role: implementation
  target: server/routes/bandTrash.ts
---

# Only the band owner deletes trashed attachments for good

Deleting an attachment from the trash for good is for the band owner; the Product itself deletes it after 30 days in the trash.
