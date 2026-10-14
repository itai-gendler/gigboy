---
appliesTo:
- type: entity
  id: setlist-session
  effect: changes
  to: Nobody leading
permits:
- related:
  - verb: leads
    entity: user
- unattended: true
references:
- kind: code
  role: implementation
  target: server/routes/setlistSessions.ts
---

# Only the leader releases the lead

The lead ends when the leader stops leading, or when the Product notices the leader's last screen has gone.
