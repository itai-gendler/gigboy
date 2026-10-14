---
kind: validation
routes:
  web: Web
steps:
- text: The User picks a file that is not a PDF, is over 20 MB, or would go past the storage limit
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::song
- text: The Product refuses the file and says why
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/bandAttachments.ts
- kind: code
  role: implementation
  target: server/lib/storageQuota.ts
---

# Not a PDF, too large or over the storage limit

## Trigger

The file cannot be attached.

## Outcome

Nothing is stored.
