---
kind: validation
routes:
  web: Web
steps:
- text: The User drags in a photo that would go past the storage limit
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::press-kit
- text: The Product refuses the photo and says how much storage is used
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::press-kit
references:
- kind: code
  role: implementation
  target: server/lib/storageQuota.ts
---

# Over the storage limit

## Trigger

The band is out of storage.

## Outcome

The photo is not stored.
