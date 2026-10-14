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

# Empty the trash

The band owner permanently deletes everything in the band's trash.
