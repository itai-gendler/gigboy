---
appliesTo:
- type: capability
  id: restore-song-version
- type: capability
  id: browse-song-history
references:
- kind: code
  role: implementation
  target: server/routes/songRevisions.ts
---

# Restoring a version saves a new version

Restoring keeps every later version in the history and adds the restored state as the newest.
