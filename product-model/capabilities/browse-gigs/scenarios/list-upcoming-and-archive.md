---
kind: alternative
routes:
  web: Web
steps:
- text: The User switches the gigs to Cards or List
  kind: actor
  actor: user
  entities:
  - entity: gig
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::gigs
- text: The Product shows upcoming gigs soonest first and folds past gigs into the archive, newest first
  kind: product
  actor: user
  entities:
  - entity: gig
    effect: reads
    facts:
    - Title
    - On stage
    - Venue
    - Status
  contexts:
    web:
      place: web::bands::gigs
references:
- kind: code
  role: implementation
  target: src/pages/BandGigsPage.tsx
---

# Cards or list, with the archive

## Trigger

A member wants an overview rather than a calendar.

## Outcome

Upcoming gigs are listed; past gigs wait in the collapsed archive until opened.
