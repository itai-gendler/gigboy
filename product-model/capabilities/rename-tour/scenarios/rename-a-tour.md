---
kind: primary
routes:
  web: Web
steps:
- text: The User edits the tour name on the tour's page
  kind: actor
  actor: user
  entities:
  - entity: tour
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::tour
- text: The Product saves the new name
  kind: product
  actor: user
  entities:
  - entity: tour
    effect: changes
    facts:
    - Name
  contexts:
    web:
      place: web::bands::tour
references:
- kind: code
  role: implementation
  target: src/context/BandsContext.tsx
---

# Rename a tour

## Trigger

A tour needs a better name.

## Outcome

The tour carries the new name in the sidebar and on its gigs.
