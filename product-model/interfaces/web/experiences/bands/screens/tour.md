---
entities:
- entity: tour
  shows:
  - Name
  collects:
  - Name
- entity: gig
  shows: &id001
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
  collects: *id001
- entity: setlist
  shows:
  - Name
- entity: technical-rider
  shows:
  - Name
- entity: press-kit
  shows:
  - Name
entryPoints:
- web: /bands/:id/tours/:tourId
references:
- kind: code
  role: implementation
  target: src/pages/BandGigsPage.tsx
---

# Tour

One tour's gigs, as a calendar, cards or a list.
