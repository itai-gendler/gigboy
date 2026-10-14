---
appliesTo:
- type: entity
  id: band
  effect: changes
permits:
- related:
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
- kind: code
  role: implementation
  target: src/pages/BandSettingsPage.tsx
---

# Only band editors change the band name and bio

Renaming the band or changing its bio takes an Editor membership in it. The band settings page itself opens only for the owner; editors rename the band from the library title.
