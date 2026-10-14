---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Leave on their own row of the member list
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::band-members
- text: The Product removes the User's membership
  kind: product
  actor: user
  entities:
  - entity: membership
    effect: removes
  contexts:
    web:
      place: web::bands::band-members
references:
- kind: code
  role: implementation
  target: server/routes/bands.ts
- kind: code
  role: implementation
  target: src/components/BandManagementPanel.tsx
---

# Leave the band

## Trigger

A member is done with a band.

## Outcome

The band disappears from their band switcher and their calendar link for it stops working.
