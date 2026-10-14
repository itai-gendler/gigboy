---
kind: edge
routes:
  web: Web
steps:
- text: The User chooses Restore on an item whose original is already back
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::bands::trash
- text: The Product refuses and says the item may already have been restored
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::trash
references:
- kind: code
  role: implementation
  target: server/lib/trash.ts#restoreTrashRow
---

# Already restored

## Trigger

A trashed item is restored twice.

## Outcome

Nothing is duplicated.
