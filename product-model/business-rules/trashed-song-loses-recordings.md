---
appliesTo:
- type: capability
  id: delete-song
- type: capability-scenario
  id: restore-song
references:
- kind: code
  role: implementation
  target: server/routes/bandSongs.ts
- kind: code
  role: implementation
  target: server/lib/songFiles.ts
---

# Moving a song to trash deletes its recordings and attachments for good

Only the song's chart and details wait in the trash. Its recordings and PDF attachments are deleted at once, and its notes, history and personal transposes go with it, so restoring the song does not bring them back.
