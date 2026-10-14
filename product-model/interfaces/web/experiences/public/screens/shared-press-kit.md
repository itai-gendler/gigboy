---
entities:
- entity: press-kit
  shows:
  - Name
  - Text
  - Images
  - Shown videos
  - Pre-save release
  - Release date
  - Shown pre-save links
  - Tour dates
- entity: press-kit-image
  shows:
  - Title
  - Picture
- entity: band
  shows:
  - Name
  - Logo
- entity: gig
  shows:
  - Title
  - On stage
  - Venue
  - Address
  - Tour
entryPoints:
- web: /public/press-kit/:token
references:
- kind: code
  role: implementation
  target: src/pages/PublicBandPressKitPage.tsx
---

# Shared press kit

A press kit as anyone with its public link sees it, with a ZIP download.
