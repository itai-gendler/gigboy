---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses to delete the rider and confirms
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
- text: The Product moves the rider to the trash and detaches it from every gig that used it
  kind: product
  actor: user
  entities:
  - entity: technical-rider
    effect: changes
    from: Active
    to: In trash
    facts: []
  - entity: gig
    effect: changes
    facts:
    - Technical rider
  contexts:
    web:
      place: web::bands::technical-rider
references:
- kind: code
  role: implementation
  target: server/routes/bandRiders.ts
- kind: code
  role: implementation
  target: server/db/schema.ts#gigs
---

# Move a rider to trash

## Trigger

A rider is no longer needed.

## Outcome

The rider waits in the trash for 30 days.
