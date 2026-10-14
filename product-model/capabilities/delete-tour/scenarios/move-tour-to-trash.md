---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete tour on the tour's page and confirms
  kind: actor
  actor: user
  entities:
  - entity: tour
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::tour
- text: The Product moves the tour to the trash and ungroups its gigs
  kind: product
  actor: user
  entities:
  - entity: tour
    effect: changes
    from: Active
    to: In trash
    facts: []
  - entity: gig
    effect: changes
    facts:
    - Tour
  contexts:
    web:
      place: web::bands::tour
- text: The Product opens All gigs
  kind: product
  actor: user
  entities:
  - entity: gig
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::gigs
references:
- kind: code
  role: implementation
  target: server/routes/bandResources.ts
- kind: code
  role: implementation
  target: server/db/schema.ts#gigs
---

# Move a tour to trash

## Trigger

A tour grouping is no longer wanted.

## Outcome

Every gig is still on the calendar without a tour; the tour waits in the trash.
