---
kind: primary
routes:
  web: Web
steps:
- text: The leading User picks Solo or Follow, or leaves concert mode
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::concert-mode
- text: The Product releases the lead and tells every follower that nobody is leading
  kind: product
  actor: user
  entities:
  - entity: setlist-session
    effect: changes
    from: Led
    to: Nobody leading
    facts: []
  contexts:
    web:
      place: web::bands::concert-mode
references:
- kind: code
  role: implementation
  target: server/routes/setlistSessions.ts
---

# Stop leading

## Trigger

The leader is done leading.

## Outcome

Followers see that nobody is leading; the last position is kept for the next leader.
