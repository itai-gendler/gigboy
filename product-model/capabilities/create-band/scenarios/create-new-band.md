---
kind: primary
routes:
  web: Web
steps:
- text: The User names a new band from the band switcher or their profile
  kind: actor
  actor: user
  entities:
  - entity: band
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands
- text: The Product creates the band owned by the User, with the User as its first editor
  kind: product
  actor: user
  entities:
  - entity: band
    effect: creates
    facts:
    - Name
  - entity: membership
    effect: creates
    facts:
    - Role
    - Joined
    with: band
  contexts:
    web:
      place: web::bands
- text: The Product opens the new band's empty library
  kind: product
  actor: user
  entities:
  - entity: band
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::library
references:
- kind: code
  role: implementation
  target: server/routes/bands.ts
- kind: code
  role: implementation
  target: src/components/Sidebar.tsx
---

# Create a band

## Trigger

A user starts a new band in Gigboy.

## Outcome

The user owns the new band, is its only member, and is in its library.
