---
kind: primary
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
- text: The Product shows who leads and moves the User's screen to the leader's song and page
  kind: product
  actor: user
  entities:
  - entity: setlist-session
    effect: reads
    facts:
    - Song position
    - Page position
    - Transpose
  - entity: account
    effect: reads
    facts:
    - Full name
    - Username
    - Avatar
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::concert-mode
- text: The Product plays the chart in the leader's transpose instead of the User's own
  kind: product
  actor: user
  entities:
  - entity: setlist-session
    effect: reads
    facts:
    - Transpose
  contexts:
    web:
      place: web::bands::concert-mode
references:
- kind: code
  role: implementation
  target: src/components/ConcertModeView.tsx
- kind: code
  role: implementation
  target: server/routes/setlistSessions.ts
---

# Follow the leader

## Trigger

The band plays the set together.

## Outcome

The follower's screen keeps pace with the leader; their own transpose comes back when they stop following.
