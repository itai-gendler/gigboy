---
kind: validation
routes:
  web: Web
steps:
- text: The User saves a gig whose tour, setlist, rider or press kit is not one of their own
  kind: actor
  actor: user
  entities:
  - entity: setlist
    effect: reads
    facts: []
  - entity: tour
    effect: reads
    facts: []
  - entity: gig
    effect: reads
    facts: []
  - entity: press-kit
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::gigs
- text: The Product refuses and names the attachment it could not find
  kind: product
  actor: user
  entities:
  - entity: attachment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::gigs
references:
- kind: code
  role: implementation
  target: server/routes/bandGigs.ts#attachmentsBelongToBand
---

# Another band's setlist refused

## Trigger

A gig is saved with something from outside the band.

## Outcome

The gig is unchanged.
