---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Restore on a trashed setlist
  kind: actor
  actor: user
  entities:
  - entity: setlist
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::trash
- text: The Product puts the setlist back with its songs and stage notes
  kind: product
  actor: user
  entities:
  - entity: setlist
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

# Restore a setlist

## Trigger

A setlist was deleted by mistake.

## Outcome

The setlist is back in the sidebar; gigs it was attached to stay without it.
