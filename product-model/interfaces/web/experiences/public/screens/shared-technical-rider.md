---
entities:
- entity: technical-rider
  shows:
  - Name
  - Stage plot
  - Input list
  - Drawing
  - Logistics
  - Hospitality
- entity: band
  shows:
  - Name
  - Logo
entryPoints:
- web: /public/bands/:bandId/riders/:riderId
references:
- kind: code
  role: implementation
  target: src/pages/PublicBandRiderPage.tsx
---

# Shared technical rider

A technical rider as anyone with its public link sees it, with a ZIP download.
