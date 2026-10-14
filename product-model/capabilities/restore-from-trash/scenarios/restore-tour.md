---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Restore on a trashed tour
  kind: actor
  actor: user
  entities:
  - entity: tour
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::trash
- text: The Product puts the tour back under Tours
  kind: product
  actor: user
  entities:
  - entity: tour
    effect: changes
    from: In trash
    to: Active
    facts: []
  contexts:
    web:
      place: web::bands::trash
references:
- kind: code
  role: implementation
  target: server/lib/trash.ts#restoreTrashRow
---

# Restore a tour

## Trigger

A tour was deleted by mistake.

## Outcome

The tour is back, empty: its former gigs stay ungrouped until edited.
