---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Reset to default on a chord with a custom voicing
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
- text: The Product drops the band's voicing for that chord
  kind: product
  actor: user
  entities:
  - entity: chord-voicing
    effect: removes
  - entity: band
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/bandChordVoicings.ts
---

# Reset to default

## Trigger

The custom fingering is no longer wanted.

## Outcome

The built-in diagram shows again.
