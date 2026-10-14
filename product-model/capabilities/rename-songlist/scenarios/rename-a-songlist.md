---
kind: primary
routes:
  web: Web
steps:
- text: The User edits the songlist name
  kind: actor
  actor: user
  entities:
  - entity: songlist
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::songlist
- text: The Product saves the new name
  kind: product
  actor: user
  entities:
  - entity: songlist
    effect: changes
    facts:
    - Name
  contexts:
    web:
      place: web::bands::songlist
references:
- kind: code
  role: implementation
  target: src/context/BandsContext.tsx
---

# Rename a songlist

## Trigger

A songlist needs a better name.

## Outcome

The songlist carries the new name in the sidebar.
