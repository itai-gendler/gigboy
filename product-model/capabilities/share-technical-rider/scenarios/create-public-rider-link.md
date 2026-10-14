---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Create & copy public link on the rider
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
- text: The Product shares the rider and copies its public link
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
---

# Create and copy the public link

## Trigger

A venue asks for the band's rider.

## Outcome

Anyone the link is sent to can read the rider without an account.
