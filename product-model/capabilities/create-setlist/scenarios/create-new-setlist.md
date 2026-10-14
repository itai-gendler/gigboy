---
kind: primary
routes:
  web: Web
steps:
- text: The User names a new setlist with the + next to Setlists
  kind: actor
  actor: user
  entities:
  - entity: setlist
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands
- text: The Product creates the empty setlist and opens it
  kind: product
  actor: user
  entities:
  - entity: setlist
    effect: creates
    to: Active
    facts:
    - Name
    - Songs
    - Stage notes
  contexts:
    web:
      place: web::bands::setlist
references:
- kind: code
  role: implementation
  target: src/components/Sidebar.tsx
---

# Create a setlist

## Trigger

An editor starts a setlist for a gig.

## Outcome

The empty setlist is in the sidebar and open, ready for songs.
