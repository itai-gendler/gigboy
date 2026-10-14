---
appliesTo:
- type: capability
  id: restore-from-trash
- type: capability
  id: delete-forever
references:
- kind: code
  role: implementation
  target: server/lib/trash.ts
---

# Trashed items are deleted for good after 30 days

Songs, songlists, setlists, gigs, tours, press kits, press kit images, technical riders and attachments stay restorable in the band trash for 30 days, then the Product deletes them for good.
