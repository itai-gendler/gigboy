---
appliesTo:
- type: entity
  id: press-kit-image
  effect: creates
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
  target: server/routes/bandPressKitImages.ts
---

# Only band editors add press kit images

Adding a press kit image takes an Editor membership in the band.
