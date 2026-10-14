---
kind: primary
routes:
  web: Web
steps:
- text: The User presses Add gig on the gigs page
  kind: actor
  actor: user
  entities:
  - entity: gig
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::gigs
- text: The User enters the title, on-stage time and any schedule, venue, contact, notes, tour, setlist, rider and press kit
  kind: actor
  actor: user
  entities:
  - entity: setlist
    effect: reads
    facts:
    - Name
  - entity: tour
    effect: reads
    facts:
    - Name
  - entity: press-kit
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::gigs
- text: The Product checks the attached tour and setlist and saves the gig
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
  - entity: setlist
    effect: reads
    facts: []
  - entity: tour
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::gigs
- text: The Product shows the gig in its month
  kind: product
  actor: user
  entities:
  - entity: gig
    effect: reads
    facts:
    - Title
    - On stage
  contexts:
    web:
      place: web::bands::gigs
references:
- kind: code
  role: implementation
  target: src/pages/BandGigsPage.tsx
- kind: code
  role: implementation
  target: server/routes/bandGigs.ts
---

# Add a gig

## Trigger

The band books a show.

## Outcome

The gig is on every member's gig calendar and in their subscribed calendar apps, Confirmed unless another status was picked.

## Edge cases

- A new gig starts at the next full hour in the time zone of the device it is entered on.
- Picking Tentative or Cancelled as the status is shown on the gig and passed to calendar apps.
