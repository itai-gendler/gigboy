---
kind: alternative
routes:
  web: Web
steps:
- text: The User sets the status of a gig to Cancelled and saves
  kind: actor
  actor: user
  entities:
  - entity: gig
    effect: reads
    facts:
    - Status
  contexts:
    web:
      place: web::bands::gigs
- text: The Product saves the status
  kind: product
  actor: user
  entities:
  - entity: gig
    effect: changes
    facts:
    - Status
  contexts:
    web:
      place: web::bands::gigs
references:
- kind: code
  role: implementation
  target: server/routes/bandGigs.ts
- kind: code
  role: implementation
  target: server/lib/ics.ts
---

# Mark a gig cancelled

## Trigger

A show falls through but the band wants to keep its record.

## Outcome

The gig stays on the calendar marked Cancelled, and calendar apps show it as cancelled.
