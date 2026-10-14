---
appliesTo:
- type: entity
  id: membership
  effect: removes
permits:
- related:
  - verb: has
    entity: band
  - verb: owns
    entity: user
- related:
  - verb: holds
    entity: user
references:
- kind: code
  role: implementation
  target: server/routes/bands.ts
---

# Only the band owner removes members; anyone may leave

The band owner may remove any other member, and every member may remove themselves by leaving.
