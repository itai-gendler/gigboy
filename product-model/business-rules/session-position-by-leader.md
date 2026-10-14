---
appliesTo:
- type: entity
  id: setlist-session
  effect: changes
  facts:
  - Song position
  - Page position
  - Transpose
permits:
- related:
  - verb: leads
    entity: user
references:
- kind: code
  role: implementation
  target: server/routes/setlistSessions.ts
---

# Only the leader moves a setlist session

The song, page and transpose of a setlist session change only through the current leader's navigation.
