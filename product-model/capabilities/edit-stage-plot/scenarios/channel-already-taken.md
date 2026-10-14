---
kind: validation
routes:
  web: Web
steps:
- text: The User gives an item a channel number another input already has
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::technical-rider
- text: The Product keeps the item's previous channel
  kind: product
  actor: user
  entities:
  - entity: technical-rider
    effect: reads
    facts:
    - Input list
  contexts:
    web:
      place: web::bands::technical-rider
references:
- kind: code
  role: implementation
  target: src/components/StageplotEditor.tsx
---

# Channel already taken

## Trigger

Two inputs would share a desk channel.

## Outcome

Each channel number stays with one input; outputs are numbered separately.
