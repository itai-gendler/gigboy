---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Restore on a trashed technical rider
  kind: actor
  actor: user
  entities:
  - entity: technical-rider
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::trash
- text: The Product puts the rider back with its stage plot and notes
  kind: product
  actor: user
  entities:
  - entity: technical-rider
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

# Restore a technical rider

## Trigger

A rider was deleted by mistake.

## Outcome

The rider is back in the sidebar.
