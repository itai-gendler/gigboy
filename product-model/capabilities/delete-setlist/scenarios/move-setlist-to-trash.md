---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses to delete the setlist and confirms
  kind: actor
  actor: user
  entities:
  - entity: setlist
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::setlist
- text: The Product moves the setlist to the trash and detaches it from every gig that used it
  kind: product
  actor: user
  entities:
  - entity: setlist
    effect: changes
    from: Active
    to: In trash
    facts: []
  - entity: gig
    effect: changes
    facts:
    - Setlist
  contexts:
    web:
      place: web::bands::setlist
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
  target: server/routes/bandResources.ts
- kind: code
  role: implementation
  target: server/db/schema.ts#gigs
---

# Move a setlist to trash

## Trigger

A setlist is no longer needed.

## Outcome

The setlist waits in the trash for 30 days; gigs that pointed at it no longer show a setlist, even after a restore.
