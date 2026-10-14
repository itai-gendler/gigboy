---
entities:
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
- entity: tour
  shows:
  - Name
- entity: setlist
  shows:
  - Name
- entity: technical-rider
  shows:
  - Name
- entity: press-kit
  shows:
  - Name
- entity: calendar-link
  shows:
  - Link
entryPoints:
- web: /bands/:id/gigs
references:
- kind: code
  role: implementation
  target: src/pages/BandGigsPage.tsx
- kind: code
  role: implementation
  target: src/components/GigsCalendar.tsx
---

# Gigs

Every gig of the band across all tours, as a calendar, cards or a list, with past gigs in an archive.
