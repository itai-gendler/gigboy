---
kind: primary
routes:
  web: Web
steps:
- text: The User names a new songlist with the + next to Songlists
  kind: actor
  actor: user
  entities:
  - entity: songlist
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands
- text: The Product creates the empty songlist and opens it
  kind: product
  actor: user
  entities:
  - entity: songlist
    effect: creates
    to: Active
    facts:
    - Name
    - Songs
  contexts:
    web:
      place: web::bands::songlist
references:
- kind: code
  role: implementation
  target: src/components/Sidebar.tsx
---

# Create a songlist

## Trigger

An editor wants a new collection of songs.

## Outcome

The empty songlist is in the sidebar and open.
