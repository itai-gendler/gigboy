---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Restore on a trashed press kit image
  kind: actor
  actor: user
  entities:
  - entity: press-kit-image
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::bands::trash
- text: The Product puts the image back in the library and in the press kits that had picked it
  kind: product
  actor: user
  entities:
  - entity: press-kit-image
    effect: changes
    from: In trash
    to: Active
    facts: []
  - entity: press-kit
    effect: changes
    facts:
    - Images
  contexts:
    web:
      place: web::bands::trash
references:
- kind: code
  role: implementation
  target: server/lib/trash.ts#restoreTrashRow
---

# Restore a press kit image

## Trigger

A photo was deleted by mistake.

## Outcome

The image is back in the library and in its kits.
