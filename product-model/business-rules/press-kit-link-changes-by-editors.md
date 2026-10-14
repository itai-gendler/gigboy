---
appliesTo:
- type: entity
  id: press-kit-link
  effect: changes
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

# Only band editors disable a press kit link

Disabling the public link to a press kit takes an Editor membership in the band.
