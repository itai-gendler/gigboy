---
kind: primary
routes:
  web: Web
steps:
- text: The User writes the logistics and hospitality notes
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::technical-rider
- text: The Product saves the notes
  kind: product
  actor: user
  entities:
  - entity: technical-rider
    effect: changes
    facts:
    - Logistics
    - Hospitality
  contexts:
    web:
      place: web::bands::technical-rider
references:
- kind: code
  role: implementation
  target: src/components/InputListEditor.tsx
- kind: code
  role: implementation
  target: server/routes/bandRiders.ts
---

# Write logistics and hospitality notes

## Trigger

The band has needs beyond the stage, such as parking or catering.

## Outcome

The rider carries the notes.
