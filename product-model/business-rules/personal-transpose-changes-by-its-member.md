---
appliesTo:
- type: entity
  id: personal-transpose
  effect: changes
permits:
- related:
  - verb: keeps
    entity: user
references:
- kind: code
  role: implementation
  target: server/routes/songMemberPrefs.ts
---

# Only its member changes a personal transpose

A member's transpose for a song is theirs alone to change.
