---
availability:
- place: web::bands
domain: trash
references:
- kind: code
  role: implementation
  target: server/routes/bandTrash.ts
- kind: code
  role: implementation
  target: server/lib/trash.ts#restoreTrashRow
---

# Restore from trash

An editor brings a trashed song, songlist, setlist, gig, tour, press kit, press kit image, technical rider or attachment back from the trash.
