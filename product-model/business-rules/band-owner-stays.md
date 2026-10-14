---
appliesTo:
- type: capability
  id: remove-band-member
- type: capability
  id: leave-band
references:
- kind: code
  role: implementation
  target: server/routes/bands.ts
---

# The band owner cannot be removed from the band

The owner has no way to leave or be removed; the band ends only when its owner deletes it or their account.
