---
appliesTo:
- type: entity
  id: personal-transpose
  effect: removes
permits:
- related:
  - verb: keeps
    entity: user
references:
- kind: code
  role: implementation
  target: server/routes/songMemberPrefs.ts
---

# Only its member resets a personal transpose

Only the member who keeps a transpose for a song resets it to the written key.
