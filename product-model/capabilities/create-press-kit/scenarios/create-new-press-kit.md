---
kind: primary
routes:
  web: Web
steps:
- text: The User enters a name with the + next to Press Kits
  kind: actor
  actor: user
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
references:
- kind: code
  role: implementation
  target: server/routes/bandPressKits.ts
---

# Create a press kit

## Trigger

An editor prepares material for promoters.

## Outcome

The empty press kit is in the sidebar and open for writing.
