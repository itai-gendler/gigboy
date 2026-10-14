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
  target: src/components/TrashView.tsx
---

# Delete from trash for good

The band owner permanently deletes one trashed item before its 30 days are up.
