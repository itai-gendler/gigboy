---
kind: validation
routes:
  web: Web
steps:
- text: The User posts an empty comment or one over 2000 characters
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::song
- text: The Product refuses it
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/recordingComments.ts
---

# Empty or too long

## Trigger

A comment is empty or too long.

## Outcome

Nothing is posted.
