---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete permanently on a trashed song
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
- text: The Product deletes the song for good
  kind: product
  actor: user
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
  target: server/routes/bandTrash.ts
---

# Delete a trashed song for good

## Trigger

The owner clears out something that should not come back.

## Outcome

The song can no longer be restored.
