---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete on a gig and confirms
  kind: actor
  actor: user
  entities:
  - entity: gig
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::bands::gigs
- text: The Product moves the gig to the trash
  kind: product
  actor: user
  entities:
  - entity: gig
    effect: changes
    from: Active
    to: In trash
    facts: []
  contexts:
    web:
      place: web::bands::gigs
references:
- kind: code
  role: implementation
  target: server/routes/bandResources.ts
---

# Move a gig to trash

## Trigger

A gig was entered by mistake or is no longer wanted.

## Outcome

The gig leaves the calendar, the subscribed calendars, and waits in the trash for 30 days.
