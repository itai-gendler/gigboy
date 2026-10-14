---
appliesTo:
- type: entity
  id: chord-voicing
  effect: changes
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
  target: server/routes/bandChordVoicings.ts
---

# Only band editors change chord voicings

A band's chord voicings are managed by members with an Editor membership.
