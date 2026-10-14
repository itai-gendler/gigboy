---
availability:
- place: web::bands
domain: setlists
references:
- kind: code
  role: implementation
  target: server/routes/setlistSessions.ts
- kind: code
  role: implementation
  target: src/hooks/useSetlistSession.ts
---

# Stop leading

The leader of a setlist gives up the lead, so followers wait for a new leader.
