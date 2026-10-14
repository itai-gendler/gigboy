---
kind: primary
routes:
  web: Web
steps:
- text: The Visitor opens the public link
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::public::shared-press-kit
- text: The Product shows the band name and logo, the kit text, its images, shown videos and pre-save links, and its tour dates
  kind: product
  actor: visitor
  entities:
  - entity: press-kit-link
    effect: reads
    facts: []
  - entity: band
    effect: reads
    facts:
    - Name
    - Logo
  - entity: press-kit
    effect: reads
    facts:
    - Name
    - Text
    - Images
    - Shown videos
    - Pre-save release
    - Release date
    - Shown pre-save links
    - Tour dates
  - entity: press-kit-image
    effect: reads
    facts:
    - Title
    - Picture
  - entity: gig
    effect: reads
    facts:
    - Title
    - On stage
    - Venue
    - Address
    - Tour
    - Status
  - entity: tour
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::shared-press-kit
- text: The Visitor downloads the kit as a ZIP
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::public::shared-press-kit
references:
- kind: code
  role: implementation
  target: server/routes/publicPressKits.ts
- kind: code
  role: implementation
  target: src/pages/PublicBandPressKitPage.tsx
---

# Read a shared press kit

## Trigger

A promoter opens the link the band sent.

## Outcome

The promoter reads the kit, with the confirmed upcoming gigs grouped by tour, and has its files.
