---
kind: primary
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
- text: The Product shows the band name and logo, the stage plot with its numbered items, and the logistics and hospitality notes
  kind: product
  actor: visitor
  entities:
  - entity: band
    effect: reads
    facts:
    - Name
    - Logo
  - entity: technical-rider
    effect: reads
    facts:
    - Name
    - Stage plot
    - Input list
    - Drawing
    - Logistics
    - Hospitality
    - Shared
  contexts:
    web:
      place: web::public::shared-technical-rider
references:
- kind: code
  role: implementation
  target: src/pages/PublicBandRiderPage.tsx
---

# Read a shared rider

## Trigger

A sound engineer opens the link the band sent.

## Outcome

The engineer can plan the stage and the desk.
