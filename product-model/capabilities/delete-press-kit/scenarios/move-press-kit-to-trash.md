---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete press kit and confirms
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
- text: The Product moves the press kit to the trash and detaches it from every gig that used it
  kind: product
  actor: user
  entities:
  - entity: press-kit
    effect: changes
    from: Active
    to: In trash
    facts: []
  - entity: gig
    effect: changes
    facts:
    - Press kit
  contexts:
    web:
      place: web::bands::press-kit
references:
- kind: code
  role: implementation
  target: server/routes/bandPressKits.ts
- kind: code
  role: implementation
  target: server/db/schema.ts#gigs
---

# Move a press kit to trash

## Trigger

A kit is no longer needed.

## Outcome

The kit waits in the trash for 30 days, and its public link no longer opens it.
