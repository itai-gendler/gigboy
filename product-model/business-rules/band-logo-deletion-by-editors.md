---
appliesTo:
- type: entity
  id: band-logo
  effect: removes
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
  target: server/routes/bandLogos.ts
---

# Only band editors delete band logos

Deleting from the band's logo library takes an Editor membership.
