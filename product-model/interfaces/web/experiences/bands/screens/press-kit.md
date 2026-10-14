---
entities:
- entity: press-kit
  shows: &id001
  - Name
  - Text
  - Images
  - Videos
  - Shown videos
  - Pre-save release
  - Release date
  - Pre-save links
  - Shown pre-save links
  - Tour dates
  collects: *id001
- entity: press-kit-image
  shows:
  - Title
  - Picture
  collects:
  - Picture
- entity: press-kit-link
  shows:
  - Link
- entity: gig
  shows:
  - Title
  - On stage
  - Venue
  - Status
- entity: tour
  shows:
  - Name
entryPoints:
- web: /bands/:id/press-kit/:kitId
references:
- kind: code
  role: implementation
  target: src/components/PressKitView.tsx
---

# Press kit

One press kit: its text, picked images, videos, pre-save release and tour dates, the band's image library, and its public link.
