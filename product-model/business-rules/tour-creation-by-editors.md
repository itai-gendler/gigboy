---
appliesTo:
- type: entity
  id: tour
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
  target: server/routes/bandResources.ts#buildBandCrudRouter
---

# Only band editors add tours

Adding a tour to a band takes an Editor membership in that band.
