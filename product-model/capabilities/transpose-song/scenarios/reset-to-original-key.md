---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Reset to original key
  kind: actor
  actor: user
  entities:
  - entity: personal-transpose
    effect: reads
    facts:
    - Semitones
  contexts:
    web:
      place: web::bands::song
- text: The Product drops the User's own shift for this song
  kind: product
  actor: user
  entities:
  - entity: personal-transpose
    effect: removes
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: src/components/SongView.tsx
---

# Reset to the original key

## Trigger

A member wants the chart as written again.

## Outcome

The song shows in its written key for this member.
