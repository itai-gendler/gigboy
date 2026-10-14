---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Remove logo and confirms
  kind: actor
  actor: user
  entities:
  - entity: band
    effect: reads
    facts:
    - Logo
  contexts:
    web:
      place: web::bands::band-settings
- text: The Product clears the band logo, keeping the image in the library
  kind: product
  actor: user
  entities:
  - entity: band
    effect: changes
    facts:
    - Logo
  - entity: band-logo
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::band-settings
references:
- kind: code
  role: implementation
  target: server/routes/bandLogos.ts
---

# Remove the logo

## Trigger

The band wants no logo for now.

## Outcome

Shared pages show no logo.
