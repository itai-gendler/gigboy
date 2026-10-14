---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the metronome on the song and presses play
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Tempo
  contexts:
    web:
      place: web::bands::song
- text: The Product clicks and pulses at the song's tempo
  kind: product
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Tempo
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: src/components/VisualMetronome.tsx
---

# Play the click at the song's tempo

## Trigger

A member rehearses in time.

## Outcome

The click and the beat dots run at the chosen tempo.

## Edge cases

- The tempo changes with minus and plus or by tapping it in.
- The click can be muted to keep only the visual pulse.
