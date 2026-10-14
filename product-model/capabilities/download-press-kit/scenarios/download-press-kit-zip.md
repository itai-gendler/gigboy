---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Download ZIP on the press kit
  kind: actor
  actor: user
  entities:
  - entity: press-kit
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::press-kit
- text: The Product packs the text, picked images, links, release and tour dates into a ZIP
  kind: product
  actor: user
  entities:
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
  - entity: tour
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::press-kit
references:
- kind: code
  role: implementation
  target: src/lib/pressKitZip.ts
---

# Download the kit as a ZIP

## Trigger

A promoter wants the files, not a link.

## Outcome

The member has a ZIP of the kit to attach or send on.
