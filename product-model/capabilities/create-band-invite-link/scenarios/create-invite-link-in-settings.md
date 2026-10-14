---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Create invite link in band settings
  kind: actor
  actor: user
  entities:
  - entity: band
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::band-settings
- text: The Product creates a link that grants the Editor role and works for seven days
  kind: product
  actor: user
  entities:
  - entity: band-invite
    effect: creates
    facts:
    - Link
    - Role
    - Expires
  contexts:
    web:
      place: web::bands::band-settings
references:
- kind: code
  role: implementation
  target: src/pages/BandSettingsPage.tsx
---

# Create an invite link in band settings

## Trigger

The band owner invites people from band settings.

## Outcome

A new link is ready to share.
