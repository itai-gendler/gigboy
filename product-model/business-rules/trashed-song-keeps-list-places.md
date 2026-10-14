---
appliesTo:
- type: capability
  id: delete-song
- type: capability-scenario
  id: restore-song
references:
- kind: code
  role: implementation
  target: src/pages/BandDetailPage.tsx
- kind: code
  role: implementation
  target: server/lib/trash.ts#restoreTrashRow
---

# A trashed song leaves every list until it is restored

A song in the trash disappears from the setlists and songlists it was on, and comes back in the same places when restored.
