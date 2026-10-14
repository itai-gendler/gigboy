---
kind: edge
routes:
  web: Web
steps:
- text: The leader's last open concert screen closes or loses its connection
  kind: condition
  unattended: true
  entities:
  - entity: setlist-session
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::concert-mode
- text: The Product releases the lead and tells every follower that nobody is leading
  kind: product
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

# The leader drops off

## Trigger

The leader's device sleeps, goes offline or closes the app.

## Outcome

Another member can take the lead; followers stay on the last position.
