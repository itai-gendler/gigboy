---
kind: alternative
routes:
  web: Web
steps:
- text: The User types words into the gig search
  kind: actor
  actor: user
  entities:
  - entity: gig
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::gigs
- text: The Product keeps the gigs where every word matches the title, venue, address, contact, notes, status, date or attached names
  kind: product
  actor: user
  entities:
  - entity: gig
    effect: reads
    facts:
    - Title
    - Venue
    - Address
    - Contact name
    - Contact phone
    - Contact email
    - Notes
    - Status
    - On stage
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

# Search gigs

## Trigger

A member looks for one show.

## Outcome

Only matching gigs show, the archive included.
