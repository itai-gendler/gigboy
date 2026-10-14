---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses to delete the songlist and confirms
  kind: actor
  actor: user
  entities:
  - entity: songlist
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::songlist
- text: The Product moves the songlist to the trash
  kind: product
  actor: user
  entities:
  - entity: songlist
    effect: changes
    from: Active
    to: In trash
    facts: []
  contexts:
    web:
      place: web::bands::songlist
- text: The Product returns the User to the library
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::library
references:
- kind: code
  role: implementation
  target: src/pages/BandDetailPage.tsx
- kind: code
  role: implementation
  target: server/routes/bandResources.ts
---

# Move a songlist to trash

## Trigger

A songlist is no longer needed.

## Outcome

The songlist is in the trash for 30 days; no song is deleted.
