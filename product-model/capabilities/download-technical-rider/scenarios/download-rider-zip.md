---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Download ZIP on the rider
  kind: actor
  actor: user
  entities:
  - entity: technical-rider
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::technical-rider
- text: The Product packs the stage plot, input list and notes into a ZIP
  kind: product
  actor: user
  entities:
  - entity: technical-rider
    effect: reads
    facts:
    - Name
    - Stage plot
    - Input list
    - Drawing
    - Logistics
    - Hospitality
  contexts:
    web:
      place: web::bands::technical-rider
references:
- kind: code
  role: implementation
  target: src/lib/pressKitZip.ts
---

# Download the rider as a ZIP

## Trigger

A venue wants the files.

## Outcome

The member has a ZIP of the rider.
