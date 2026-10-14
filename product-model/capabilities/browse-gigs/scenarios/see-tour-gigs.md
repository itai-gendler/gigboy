---
kind: alternative
routes:
  web: Web
steps:
- text: The User picks a tour under Tours
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
- text: The Product shows only that tour's gigs
  kind: product
  actor: user
  entities:
  - entity: tour
    effect: reads
    facts:
    - Name
  - entity: gig
    effect: reads
    facts:
    - Title
    - On stage
    - Venue
    - Status
    - Tour
  contexts:
    web:
      place: web::bands::tour
references:
- kind: code
  role: implementation
  target: src/pages/BandGigsPage.tsx
---

# See one tour's gigs

## Trigger

A member focuses on one tour.

## Outcome

Only the tour's gigs show, under the tour's name.
