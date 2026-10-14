---
appliesTo:
- type: entity
  id: press-kit-image
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
---

# Only the band owner deletes trashed press kit images for good

Deleting a press kit image from the trash for good is for the band owner; the Product itself deletes it after 30 days in the trash.
