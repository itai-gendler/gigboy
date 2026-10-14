---
kind: edge
routes:
  web: Web
steps:
- text: The User picks Lead in the concert settings
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::concert-mode
- text: Another member already leads the setlist
  kind: condition
  entities:
  - entity: setlist-session
    effect: reads
    facts: []
  - entity: account
    effect: reads
    facts:
    - Full name
    - Username
  - entity: setlist
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::concert-mode
- text: The Product refuses, names who is leading and switches the User to Follow
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::concert-mode
references:
- kind: code
  role: implementation
  target: server/routes/setlistSessions.ts
- kind: code
  role: implementation
  target: src/hooks/useSetlistSession.ts
---

# Someone else is already leading

## Trigger

Two members try to lead the same setlist.

## Outcome

The first leader keeps the lead; the second member sees who leads and follows them.
