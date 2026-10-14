---
kind: primary
routes:
  web: Web
steps:
- text: The User enters a name with the + next to Tours
  kind: actor
  actor: user
  entities:
  - entity: tour
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands
- text: The Product creates the tour and opens its page
  kind: product
  actor: user
  entities:
  - entity: tour
    effect: creates
    to: Active
    facts:
    - Name
  contexts:
    web:
      place: web::bands::tour
references:
- kind: code
  role: implementation
  target: src/components/Sidebar.tsx
---

# Create a tour

## Trigger

The band plans a run of shows.

## Outcome

The tour is listed under Tours and its empty page is open.
