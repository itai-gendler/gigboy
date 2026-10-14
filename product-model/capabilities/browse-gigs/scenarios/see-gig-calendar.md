---
kind: primary
routes:
  web: Web
steps:
- text: The User opens All gigs under Tours
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
      place: web::bands::gigs
- text: The Product shows the month's gigs on a calendar
  kind: product
  actor: user
  entities:
  - entity: gig
    effect: reads
    facts:
    - Title
    - On stage
    - Status
  contexts:
    web:
      place: web::bands::gigs
- text: The User picks a gig on the calendar
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
- text: The Product shows the gig's schedule, venue, contact, notes and what is attached to it
  kind: product
  actor: user
  entities:
  - entity: gig
    effect: reads
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
  contexts:
    web:
      place: web::bands::gigs
references:
- kind: code
  role: implementation
  target: src/pages/BandGigsPage.tsx
---

# See the gig calendar

## Trigger

A member checks what is coming up.

## Outcome

The member sees every gig in the month and the full details of the one they picked.
