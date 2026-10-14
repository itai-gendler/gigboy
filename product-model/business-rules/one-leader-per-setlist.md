---
appliesTo:
- type: capability
  id: lead-setlist
- type: capability
  id: stop-leading
references:
- kind: code
  role: implementation
  target: server/routes/setlistSessions.ts
---

# A setlist has one leader at a time

While a member leads a setlist, nobody else can take the lead until that member stops or drops off.
