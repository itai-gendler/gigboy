---
appliesTo:
- type: entity
  id: technical-rider
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
  target: server/routes/bandRiders.ts
---

# Only band editors add technical riders

Adding a technical rider takes an Editor membership in the band.
