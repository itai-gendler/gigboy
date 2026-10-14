---
appliesTo:
- type: entity
  id: attachment
  effect: creates
permits:
- related:
  - verb: has
    entity: song
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
  target: server/routes/bandAttachments.ts
---

# Only band editors attach files to songs

Uploading an attachment takes an Editor membership in the band.
