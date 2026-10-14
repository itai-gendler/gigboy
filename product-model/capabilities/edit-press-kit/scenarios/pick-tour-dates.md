---
kind: alternative
routes:
  web: Web
steps:
- text: The User ticks upcoming gigs, or a whole tour, under Tour dates
  kind: actor
  actor: user
  entities:
  - entity: gig
    effect: reads
    facts:
    - Title
    - On stage
    - Venue
    - Status
  - entity: tour
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::press-kit
- text: The Product keeps the picked gigs of this band as the kit's tour dates
  kind: product
  actor: user
  entities:
  - entity: press-kit
    effect: changes
    facts:
    - Tour dates
  - entity: band
    effect: reads
    facts: []
  - entity: tour
    effect: reads
    facts: []
  - entity: gig
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::press-kit
references:
- kind: code
  role: implementation
  target: server/routes/bandPressKits.ts
- kind: code
  role: implementation
  target: src/components/PressKitView.tsx
---

# Pick the tour dates to list

## Trigger

The band wants its upcoming shows on the kit.

## Outcome

The kit lists the picked gigs; on the shared page only the confirmed, upcoming ones appear.

## Edge cases

- Ticking a tour picks all of its gigs; opening it allows picking single ones.
