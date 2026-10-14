---
kind: primary
routes:
  web: Web
steps:
- text: The User edits the press kit name
  kind: actor
  actor: user
  entities:
  - entity: press-kit
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::press-kit
- text: The Product saves the new name
  kind: product
  actor: user
  entities:
  - entity: press-kit
    effect: changes
    facts:
    - Name
  contexts:
    web:
      place: web::bands::press-kit
references:
- kind: code
  role: implementation
  target: server/routes/bandPressKits.ts
---

# Rename a press kit

## Trigger

A kit needs a clearer name, such as "Festival kit".

## Outcome

The kit carries the new name.
