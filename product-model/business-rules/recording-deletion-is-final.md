---
appliesTo:
- type: capability
  id: delete-recording
- type: capability
  id: delete-song
references:
- kind: code
  role: implementation
  target: server/routes/songRecordings.ts
---

# Deleting a recording is final

Recordings do not go to the trash: a deleted take and its comments are gone at once.
