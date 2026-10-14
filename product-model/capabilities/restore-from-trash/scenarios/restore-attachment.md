---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Restore on a trashed attachment
  kind: actor
  actor: user
  entities:
  - entity: attachment
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::trash
- text: Its song is still in the library
  kind: condition
  entities:
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::trash
- text: The Product puts the attachment back on its song
  kind: product
  actor: user
  entities:
  - entity: attachment
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

# Restore an attachment

## Trigger

A PDF was deleted by mistake.

## Outcome

The PDF is back on the song.

## Edge cases

- When the song itself is gone, the Product says the attachment cannot be restored.
