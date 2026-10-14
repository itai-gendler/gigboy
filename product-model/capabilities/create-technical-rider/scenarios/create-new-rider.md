---
kind: primary
routes:
  web: Web
steps:
- text: The User enters a name with the + next to Technical Riders
  kind: actor
  actor: user
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
references:
- kind: code
  role: implementation
  target: server/routes/bandRiders.ts
---

# Create a technical rider

## Trigger

An editor prepares what venues need.

## Outcome

The empty rider is in the sidebar and open on its stage plot.
