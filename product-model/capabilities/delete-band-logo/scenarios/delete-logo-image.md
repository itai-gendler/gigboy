---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete logo on an image in the library and confirms
  kind: actor
  actor: user
  entities:
  - entity: band-logo
    effect: reads
    facts:
    - Picture
  contexts:
    web:
      place: web::bands::band-settings
- text: The Product deletes the image, and clears the band logo when it was that image
  kind: product
  actor: user
  entities:
  - entity: band-logo
    effect: removes
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
---

# Delete a logo image

## Trigger

An old logo should go.

## Outcome

The image is gone from the library and its storage is freed.
