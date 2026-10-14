---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Restore on a trashed songlist
  kind: actor
  actor: user
  entities:
  - entity: songlist
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::trash
- text: The Product puts the songlist back with its songs
  kind: product
  actor: user
  entities:
  - entity: songlist
    effect: changes
    from: In trash
    to: Active
    facts: []
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::trash
references:
- kind: code
  role: implementation
  target: server/lib/trash.ts#restoreTrashRow
---

# Restore a songlist

## Trigger

A songlist was deleted by mistake.

## Outcome

The songlist is back in the sidebar.
