---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Restore on a trashed gig
  kind: actor
  actor: user
  entities:
  - entity: gig
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::bands::trash
- text: The Product puts the gig back on the calendar without its tour, setlist, technical rider or press kit
  kind: product
  actor: user
  entities:
  - entity: gig
    effect: changes
    from: In trash
    to: Active
    facts:
    - Tour
    - Setlist
    - Technical rider
    - Press kit
  - entity: setlist
    effect: reads
    facts: []
  - entity: tour
    effect: reads
    facts: []
  - entity: press-kit
    effect: reads
    facts: []
  - entity: technical-rider
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::trash
references:
- kind: code
  role: implementation
  target: server/lib/trash.ts#restoreTrashRow
---

# Restore a gig

## Trigger

A gig was deleted by mistake.

## Outcome

The gig is back with its schedule, venue, contact, notes and status; its tour and attachments must be picked again.
