---
kind: primary
routes:
  web: Web
steps:
- text: The User edits the setlist name
  kind: actor
  actor: user
  entities:
  - entity: setlist
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::setlist
- text: The Product saves the new name
  kind: product
  actor: user
  entities:
  - entity: setlist
    effect: changes
    facts:
    - Name
  contexts:
    web:
      place: web::bands::setlist
references:
- kind: code
  role: implementation
  target: src/context/BandsContext.tsx
---

# Rename a setlist

## Trigger

A setlist needs a better name.

## Outcome

The setlist carries the new name.
