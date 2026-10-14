---
kind: primary
routes:
  web: Web
steps:
- text: The User places an instrument, drum-kit piece, amp, monitor or custom item and drags it into position
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::technical-rider
- text: The User gives the item a label, description, stand and channel number
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::technical-rider
- text: The Product saves the stage plot and its input list
  kind: product
  actor: user
  entities:
  - entity: technical-rider
    effect: changes
    facts:
    - Stage plot
    - Input list
    - Drawing
  contexts:
    web:
      place: web::bands::technical-rider
references:
- kind: code
  role: implementation
  target: src/components/StageplotEditor.tsx
---

# Place items and number their channels

## Trigger

The band documents its stage setup.

## Outcome

The stage plot shows every item with its numbered marker, and the input list follows the channel numbers.
