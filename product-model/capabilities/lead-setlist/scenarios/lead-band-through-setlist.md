---
kind: primary
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
- text: Nobody else is leading the setlist
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
- text: The Product makes the User the leader and tells every follower who leads
  kind: product
  actor: user
  entities:
  - entity: setlist-session
    effect: changes
    from: Nobody leading
    to: Led
    facts: []
  contexts:
    web:
      place: web::bands::concert-mode
- text: The User moves to the next page or song, or changes the transpose
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::concert-mode
- text: The Product records the leader's song, page and transpose and moves every follower's screen there
  kind: product
  actor: user
  entities:
  - entity: setlist-session
    effect: changes
    facts:
    - Song position
    - Page position
    - Transpose
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::concert-mode
references:
- kind: code
  role: implementation
  target: server/routes/setlistSessions.ts
- kind: code
  role: implementation
  target: src/components/ConcertModeView.tsx
---

# Lead the band through the setlist

## Trigger

One member, such as the singer, drives the band through the set.

## Outcome

Followers' screens show the leader's song, page and transpose as the leader moves.

## Edge cases

- A member who joins late as a follower lands on the position the leader last reached.
- The same member may lead from several of their own devices.
