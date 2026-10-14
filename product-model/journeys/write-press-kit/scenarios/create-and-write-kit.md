---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The User enters a name with the + next to Press Kits
  kind: actor
  actor: user
  capability: create-press-kit
  entities:
  - entity: press-kit
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands
- text: The Product creates the empty press kit and opens it
  kind: product
  actor: user
  capability: create-press-kit
  entities:
  - entity: press-kit
    effect: creates
    to: Active
    facts:
    - Name
    - Text
    - Images
    - Videos
    - Shown videos
    - Pre-save links
    - Shown pre-save links
    - Tour dates
  contexts:
    web:
      place: web::bands::press-kit
- text: The User writes the bio and ticks images from the library
  kind: actor
  actor: user
  capability: edit-press-kit
  entities:
  - entity: press-kit-image
    effect: reads
    facts:
    - Title
    - Picture
  contexts:
    web:
      place: web::bands::press-kit
- text: The Product saves the text and the picked images
  kind: product
  actor: user
  capability: edit-press-kit
  entities:
  - entity: press-kit
    effect: changes
    facts:
    - Text
    - Images
  contexts:
    web:
      place: web::bands::press-kit
---

# Create a press kit and write it

## Trigger

An editor prepares a kit for a festival application.

## Outcome

The kit has its text and images.
