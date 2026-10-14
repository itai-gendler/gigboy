---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor opens the public link to a rider
  kind: actor
  actor: visitor
  entities:
  - entity: technical-rider
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::shared-technical-rider
- text: The rider is not shared, or is in the trash
  kind: condition
  entities:
  - entity: technical-rider
    effect: reads
    facts:
    - Shared
  contexts:
    web:
      place: web::public::shared-technical-rider
- text: The Product shows that the rider is not available
  kind: product
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::public::shared-technical-rider
references:
- kind: code
  role: implementation
  target: server/routes/publicRiders.ts
---

# Rider not shared

## Trigger

Someone opens a rider link after sharing was turned off.

## Outcome

Nothing of the rider is shown.
