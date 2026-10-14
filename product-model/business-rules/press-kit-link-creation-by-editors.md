---
appliesTo:
- type: entity
  id: press-kit-link
  effect: creates
permits:
- related:
  - verb: has
    entity: press-kit
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
  target: server/routes/bandPressKitShares.ts
---

# Only band editors share a press kit

Creating the public link to a press kit takes an Editor membership in the band.
