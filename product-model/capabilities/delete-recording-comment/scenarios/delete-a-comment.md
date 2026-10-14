---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete comment
  kind: actor
  actor: user
  entities:
  - entity: recording-comment
    effect: reads
    facts:
    - Text
  contexts:
    web:
      place: web::bands::song
- text: The Product deletes the comment
  kind: product
  actor: user
  entities:
  - entity: recording-comment
    effect: removes
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/recordingComments.ts
---

# Delete a comment

## Trigger

A comment is resolved or wrong.

## Outcome

The comment is gone from the take.
