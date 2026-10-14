---
kind: edge
routes:
  web: Web
steps:
- text: The User picks Follow in the concert settings
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::concert-mode
- text: No member leads the setlist
  kind: condition
  entities:
  - entity: setlist-session
    effect: reads
    facts: []
  - entity: setlist
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::concert-mode
- text: The Product shows that nobody is leading yet and keeps the screen where the session last was
  kind: product
  actor: user
  entities:
  - entity: setlist-session
    effect: reads
    facts:
    - Song position
    - Page position
  contexts:
    web:
      place: web::bands::concert-mode
references:
- kind: code
  role: implementation
  target: src/components/ConcertModeView.tsx
---

# Nobody is leading yet

## Trigger

A member follows before anyone leads.

## Outcome

The screen waits; as soon as someone leads, it moves with them.
