---
kind: validation
routes:
  web: Web
steps:
- text: The User saves a take that would go past the storage limit
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::song
- text: The Product refuses the take and says how much storage is used
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/lib/storageQuota.ts
---

# Over the storage limit

## Trigger

The band is out of storage.

## Outcome

The take is not saved; deleting old recordings or attachments makes room.
