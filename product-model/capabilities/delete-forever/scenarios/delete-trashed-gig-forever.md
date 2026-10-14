---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Delete permanently on a trashed gig
  kind: actor
  actor: user
  entities:
  - entity: gig
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::bands::trash
- text: The Product deletes the gig for good
  kind: product
  actor: user
  entities:
  - entity: gig
    effect: removes
    from: In trash
  contexts:
    web:
      place: web::bands::trash
references:
- kind: code
  role: implementation
  target: server/routes/bandTrash.ts
---

# Delete a trashed gig for good

## Trigger

The owner removes a gig for good.

## Outcome

The gig can no longer be restored.
