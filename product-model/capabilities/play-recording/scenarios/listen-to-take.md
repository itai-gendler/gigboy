---
kind: primary
routes:
  web: Web
steps:
- text: The User presses play on a take
  kind: actor
  actor: user
  entities:
  - entity: recording
    effect: reads
    facts:
    - Name
    - Length
  contexts:
    web:
      place: web::bands::song
- text: The Product plays the take and lists its comments
  kind: product
  actor: user
  entities:
  - entity: recording
    effect: reads
    facts:
    - Audio
    - Waveform
  - entity: recording-comment
    effect: reads
    facts:
    - Text
    - Moment
    - Author
  contexts:
    web:
      place: web::bands::song
- text: The User clicks a comment pinned to a moment
  kind: actor
  actor: user
  entities:
  - entity: recording-comment
    effect: reads
    facts:
    - Moment
  contexts:
    web:
      place: web::bands::song
- text: The Product jumps the player to that moment
  kind: product
  actor: user
  entities:
  - entity: recording
    effect: reads
    facts:
    - Audio
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: src/components/SongRecorder.tsx
---

# Listen to a take

## Trigger

A member reviews a rehearsal take.

## Outcome

The member hears the take and the spots bandmates pointed out.
