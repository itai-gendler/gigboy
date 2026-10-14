---
appliesTo:
- type: entity
  id: setlist-session
  effect: changes
  to: Led
permits:
- related:
  - verb: has
    entity: setlist
  - verb: keeps
    entity: band
  - verb: has
    entity: membership
  - verb: holds
    entity: user
references:
- kind: code
  role: implementation
  target: server/routes/setlistSessions.ts
---

# Any band member may take the lead of a setlist nobody leads

Every member of the band, whatever their role, can lead its setlists in concert mode.
