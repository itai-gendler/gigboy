---
kind: primary
routes:
  web: Web
steps:
- text: The User taps a chord on the sheet, chooses Edit voicing and sets the frets
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Chart
  contexts:
    web:
      place: web::bands::song
- text: The Product keeps the fingering as the band's voicing for that chord and instrument
  kind: product
  actor: user
  entities:
  - entity: chord-voicing
    effect: creates
    facts:
    - Instrument
    - Chord
    - Fingering
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

# Set the band's fingering

## Trigger

The band plays a chord differently from the built-in diagram.

## Outcome

Every member sees the band's fingering for that chord, on every song and in concert mode.
