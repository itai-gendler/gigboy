---
kind: primary
routes:
  web: Web
steps:
- text: The User drags photos onto the image library
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::press-kit
- text: The Product stores each photo with a thumbnail in the library
  kind: product
  actor: user
  entities:
  - entity: press-kit-image
    effect: creates
    to: Active
    facts:
    - Title
    - Picture
  contexts:
    web:
      place: web::bands::press-kit
references:
- kind: code
  role: implementation
  target: server/routes/bandPressKitImages.ts
- kind: code
  role: implementation
  target: server/lib/pressKitImages.ts
---

# Drag photos in

## Trigger

The band has new promo photos.

## Outcome

The photos are in the library, ready to pick for any of the band's press kits.

## Edge cases

- Images must be JPEG, PNG, WebP or GIF of at most 10 MB.
