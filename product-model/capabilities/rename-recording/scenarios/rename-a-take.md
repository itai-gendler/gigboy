---
kind: primary
routes:
  web: Web
steps:
- text: The User renames a take
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
- text: The Product saves the new name
  kind: product
  actor: user
  entities:
  - entity: recording
    effect: changes
    facts:
    - Name
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/songRecordings.ts
---

# Rename a take

## Trigger

A take needs a clearer name, such as "Bridge, slower".

## Outcome

The take shows the new name.
