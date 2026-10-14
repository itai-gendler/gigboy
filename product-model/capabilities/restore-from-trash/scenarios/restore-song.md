---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Restore on a trashed song
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
- text: The Product puts the song back in the library, at the end of its order
  kind: product
  actor: user
  entities:
  - entity: song
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

# Restore a song

## Trigger

A song was deleted by mistake.

## Outcome

The song's chart and details are back in the library, and it reappears in the setlists and songlists it was on.

## Edge cases

- Recordings and attachments deleted with the song do not come back.
