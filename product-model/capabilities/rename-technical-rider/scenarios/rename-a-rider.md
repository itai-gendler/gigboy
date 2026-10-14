---
kind: primary
routes:
  web: Web
steps:
- text: The User edits the rider name
  kind: actor
  actor: user
  entities:
  - entity: technical-rider
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::technical-rider
- text: The Product saves the new name
  kind: product
  actor: user
  entities:
  - entity: technical-rider
    effect: changes
    facts:
    - Name
  contexts:
    web:
      place: web::bands::technical-rider
references:
- kind: code
  role: implementation
  target: server/routes/bandRiders.ts
---

# Rename a rider

## Trigger

A rider needs a clearer name, such as "Full band" or "Acoustic duo".

## Outcome

The rider carries the new name.
