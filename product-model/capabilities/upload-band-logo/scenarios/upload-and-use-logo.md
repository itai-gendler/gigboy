---
kind: primary
routes:
  web: Web
steps:
- text: The User drops an image on the logo area in band settings
  kind: actor
  actor: user
  entities:
  - entity: band
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::band-settings
- text: The Product adds the image to the logo library and makes it the band logo
  kind: product
  actor: user
  entities:
  - entity: band-logo
    effect: creates
    facts:
    - Picture
  - entity: band
    effect: changes
    facts:
    - Logo
  contexts:
    web:
      place: web::bands::band-settings
references:
- kind: code
  role: implementation
  target: server/routes/bandLogos.ts
- kind: code
  role: implementation
  target: src/context/BandsContext.tsx
---

# Upload and use a logo

## Trigger

The band has a logo.

## Outcome

The logo shows on the band's press kits and shared pages.

## Edge cases

- Logos must be JPEG, PNG, WebP or GIF of at most 5 MB, and count toward the storage limit.
