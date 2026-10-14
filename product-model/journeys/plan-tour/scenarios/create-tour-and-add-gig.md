---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The User enters a name with the + next to Tours
  kind: actor
  actor: user
  capability: create-tour
  entities:
  - entity: tour
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands
- text: The Product creates the tour and opens its page
  kind: product
  actor: user
  capability: create-tour
  entities:
  - entity: tour
    effect: creates
    to: Active
    facts:
    - Name
  contexts:
    web:
      place: web::bands::tour
- text: The User presses Add gig on the tour's page and enters the gig
  kind: actor
  actor: user
  capability: add-gig
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
- text: The Product saves the gig in the tour
  kind: product
  actor: user
  capability: add-gig
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
---

# Create a tour and add a gig

## Trigger

The band books a run of shows.

## Outcome

The tour holds its first gig.
