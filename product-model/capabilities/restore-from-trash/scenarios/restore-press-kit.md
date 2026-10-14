---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Restore on a trashed press kit
  kind: actor
  actor: user
  entities:
  - entity: press-kit
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::trash
- text: The Product puts the press kit back with its text, images, links and tour dates
  kind: product
  actor: user
  entities:
  - entity: press-kit
    effect: changes
    from: In trash
    to: Active
    facts: []
  - entity: tour
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

# Restore a press kit

## Trigger

A press kit was deleted by mistake.

## Outcome

The kit is back in the sidebar; it needs sharing again to have a public link.
