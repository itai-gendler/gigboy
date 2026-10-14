---
kind: primary
routes:
  web: Web
steps:
- text: The User changes the band name or bio in band settings
  kind: actor
  actor: user
  entities:
  - entity: band
    effect: reads
    facts:
    - Name
    - Bio
  contexts:
    web:
      place: web::bands::band-settings
- text: The Product saves the name and bio
  kind: product
  actor: user
  entities:
  - entity: band
    effect: changes
    facts:
    - Name
    - Bio
  contexts:
    web:
      place: web::bands::band-settings
references:
- kind: code
  role: implementation
  target: src/pages/BandSettingsPage.tsx
---

# Edit name and bio in band settings

## Trigger

The band owner updates how the band presents itself.

## Outcome

The band shows its new name everywhere, and its new bio.
