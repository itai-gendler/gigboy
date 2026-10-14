---
kind: edge
routes:
  web: Web
steps:
- text: A trashed item has been in the trash for 30 days
  kind: condition
  unattended: true
  entities:
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::trash
- text: The Product deletes it for good
  kind: product
  entities:
  - entity: song
    effect: removes
    from: In trash
  contexts:
    web:
      place: web::bands::trash
references:
- kind: code
  role: implementation
  target: server/lib/trash.ts#sweepExpiredBandTrash
---

# Thirty days pass

## Trigger

An item's 30 days in the trash run out.

## Outcome

The item is gone from the trash and can no longer be restored.
