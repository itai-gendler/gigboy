---
kind: validation
routes:
  web: Web
steps:
- text: The User saves without a title, or with an end time not after the on-stage time
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::gigs
- text: The Product refuses to save and says what to fix
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::gigs
references:
- kind: code
  role: implementation
  target: server/routes/bandGigs.ts#validateGigBody
- kind: code
  role: implementation
  target: src/pages/BandGigsPage.tsx
---

# Missing title or end before start

## Trigger

An editor enters an impossible gig.

## Outcome

No gig is saved; the form stays open.
