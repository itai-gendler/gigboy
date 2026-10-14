---
kind: primary
routes:
  web: Web
steps:
- text: The User writes the bio, ticks images from the library and drags them into order
  kind: actor
  actor: user
  entities:
  - entity: press-kit-image
    effect: reads
    facts:
    - Title
    - Picture
  contexts:
    web:
      place: web::bands::press-kit
- text: The Product saves the text and the picked images in their order
  kind: product
  actor: user
  entities:
  - entity: press-kit
    effect: changes
    facts:
    - Text
    - Images
  contexts:
    web:
      place: web::bands::press-kit
- text: The User adds video and pre-save links, picks which to show, and names the release and its date
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::press-kit
- text: The Product saves the links, which of them show, and the release
  kind: product
  actor: user
  entities:
  - entity: press-kit
    effect: changes
    facts:
    - Videos
    - Shown videos
    - Pre-save links
    - Shown pre-save links
    - Pre-save release
    - Release date
  contexts:
    web:
      place: web::bands::press-kit
references:
- kind: code
  role: implementation
  target: src/components/PressKitView.tsx
---

# Write the kit and pick what it shows

## Trigger

An editor builds the kit a promoter will read.

## Outcome

The kit holds the text, images, videos and pre-save release the editor picked.
