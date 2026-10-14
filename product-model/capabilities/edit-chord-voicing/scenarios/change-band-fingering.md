---
kind: alternative
routes:
  web: Web
steps:
- text: The User edits a chord that already has a custom voicing
  kind: actor
  actor: user
  entities:
  - entity: chord-voicing
    effect: reads
    facts:
    - Fingering
  contexts:
    web:
      place: web::bands::song
- text: The Product saves the new fingering
  kind: product
  actor: user
  entities:
  - entity: chord-voicing
    effect: changes
    facts:
    - Fingering
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/bandChordVoicings.ts
---

# Change the band's fingering

## Trigger

The band settles on another fingering.

## Outcome

The new fingering shows everywhere.
