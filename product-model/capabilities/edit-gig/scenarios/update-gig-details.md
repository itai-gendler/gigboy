---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Edit on a gig and changes its details
  kind: actor
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
- text: The Product saves the gig
  kind: product
  actor: user
  entities:
  - entity: gig
    effect: changes
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
  target: server/routes/bandGigs.ts
---

# Update a gig

## Trigger

Something about a show changes: a new get-in time, a venue contact, the setlist.

## Outcome

Members see the change at once; subscribed calendar apps pick it up the next time they fetch.
