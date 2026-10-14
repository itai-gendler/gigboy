---
kind: validation
routes:
  web: Web
steps:
- text: The User submits a band without a name
  kind: actor
  actor: user
  entities:
  - entity: band
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands
- text: The Product creates nothing
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands
references:
- kind: code
  role: implementation
  target: server/routes/bands.ts
---

# Band name missing

## Trigger

A user leaves the name empty.

## Outcome

No band is created.
