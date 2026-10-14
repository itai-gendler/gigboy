---
appliesTo:
- type: entity
  id: band-invite
  effect: creates
permits:
- related:
  - verb: has
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
  target: server/routes/bands.ts
---

# Only band editors create band invite links

Creating an invite link takes an Editor membership in the band.
