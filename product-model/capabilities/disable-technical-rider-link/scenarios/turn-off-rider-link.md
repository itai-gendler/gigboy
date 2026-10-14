---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Disable public link on the rider
  kind: actor
  actor: user
  entities:
  - entity: technical-rider
    effect: reads
    facts:
    - Shared
  contexts:
    web:
      place: web::bands::technical-rider
- text: The Product stops sharing the rider
  kind: product
  actor: user
  entities:
  - entity: technical-rider
    effect: changes
    facts:
    - Shared
  contexts:
    web:
      place: web::bands::technical-rider
references:
- kind: code
  role: implementation
  target: src/components/BandTechRiderPanel.tsx
- kind: code
  role: implementation
  target: server/routes/publicRiders.ts
---

# Disable the public link

## Trigger

The rider should no longer be public.

## Outcome

The public link no longer shows the rider.
