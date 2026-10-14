---
appliesTo:
- type: entity
  id: band
  effect: removes
permits:
- related:
  - verb: owns
    entity: user
references:
- kind: code
  role: implementation
  target: server/routes/bands.ts
---

# Only the band owner deletes the band

Deleting a band, and everything it keeps, is for its owner alone.
