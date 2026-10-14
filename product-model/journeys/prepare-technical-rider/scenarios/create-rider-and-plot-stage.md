---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The User enters a name with the + next to Technical Riders
  kind: actor
  actor: user
  capability: create-technical-rider
  entities:
  - entity: technical-rider
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands
- text: The Product creates the empty, unshared rider and opens it
  kind: product
  actor: user
  capability: create-technical-rider
  entities:
  - entity: technical-rider
    effect: creates
    to: Active
    facts:
    - Name
    - Stage plot
    - Drawing
    - Shared
  contexts:
    web:
      place: web::bands::technical-rider
- text: The User places the instruments and amps and numbers their channels
  kind: actor
  actor: user
  capability: edit-stage-plot
  entities: []
  contexts:
    web:
      place: web::bands::technical-rider
- text: The Product saves the stage plot and its input list
  kind: product
  actor: user
  capability: edit-stage-plot
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
---

# Create a rider and plot the stage

## Trigger

A venue asks for the band's stage setup.

## Outcome

The rider holds the stage plot.
