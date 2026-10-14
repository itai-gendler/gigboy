---
availability:
- place: web::bands
domain: tours
references:
- kind: code
  role: implementation
  target: src/pages/BandGigsPage.tsx
- kind: code
  role: implementation
  target: server/db/schema.ts#gigs
---

# Delete a tour

An editor moves a tour to the trash; its gigs stay on the calendar, no longer grouped.
