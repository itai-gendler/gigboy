---
appliesTo:
- type: capability-scenario
  id: restore-gig
- type: capability
  id: delete-gig
references:
- kind: code
  role: implementation
  target: server/lib/trash.ts#restoreTrashRow
---

# A restored gig comes back without its tour and attachments

Restoring a gig brings back its schedule, venue, contact, notes and status, but not its tour, setlist, technical rider or press kit, even when those still exist.
