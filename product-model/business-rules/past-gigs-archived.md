---
appliesTo:
- type: capability
  id: browse-gigs
  contexts:
  - place: web::bands
references:
- kind: code
  role: implementation
  target: src/pages/BandGigsPage.tsx
---

# A gig moves to the archive once its on-stage time has passed

Upcoming gigs are those whose on-stage time is still ahead; earlier gigs sit in the archive.
