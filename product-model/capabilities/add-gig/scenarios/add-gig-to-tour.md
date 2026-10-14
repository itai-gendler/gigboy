---
kind: alternative
routes:
  web: Web
steps:
- text: The User presses Add gig on a tour's page
  kind: actor
  actor: user
  entities:
  - entity: tour
    effect: reads
    facts:
    - Name
  - entity: gig
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::tour
- text: The User enters the gig details with the tour already chosen
  kind: actor
  actor: user
  entities:
  - entity: tour
    effect: reads
    facts: []
  - entity: gig
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::tour
- text: The Product saves the gig in that tour
  kind: product
  actor: user
  entities:
  - entity: gig
    effect: creates
    to: Active
    facts:
    - Title
    - On stage
    - Ends
    - Get in
    - Sound check
    - Time zone
    - Venue
    - Address
    - Contact name
    - Contact phone
    - Contact email
    - Notes
    - Status
    - Tour
    - Setlist
    - Technical rider
    - Press kit
  - entity: tour
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::tour
references:
- kind: code
  role: implementation
  target: src/pages/BandGigsPage.tsx
---

# Add a gig from a tour's page

## Trigger

An editor fills in a tour.

## Outcome

The gig is listed under the tour and on the band calendar.
