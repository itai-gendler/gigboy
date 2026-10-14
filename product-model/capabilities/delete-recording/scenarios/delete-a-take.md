---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete on a take and confirms
  kind: actor
  actor: user
  entities:
  - entity: recording
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::song
- text: The Product deletes the take and its comments for good
  kind: product
  actor: user
  entities:
  - entity: recording
    effect: removes
  - entity: recording-comment
    effect: removes
    with: recording
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/songRecordings.ts
---

# Delete a take

## Trigger

A take is no longer useful.

## Outcome

The take and its comments are gone and its storage is freed; it does not go to the trash.
