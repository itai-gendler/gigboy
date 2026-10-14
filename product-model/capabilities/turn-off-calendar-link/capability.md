---
availability:
- place: web::bands
domain: tours
references:
- kind: code
  role: implementation
  target: server/routes/bandCalendarFeed.ts
- kind: code
  role: implementation
  target: src/pages/BandGigsPage.tsx
---

# Turn off a calendar link

A member turns off their calendar link, so their calendar app stops receiving the band's gigs.
