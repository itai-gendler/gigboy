---
kind: primary
routes:
  web: Web
steps:
- text: The User presses play on the setlist
  kind: actor
  actor: user
  entities:
  - entity: setlist
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::setlist
- text: The Product shows the first song with its place in the setlist, its stage note and the User's own transpose
  kind: product
  actor: user
  entities:
  - entity: setlist
    effect: reads
    facts:
    - Songs
    - Stage notes
  - entity: song
    effect: reads
    facts:
    - Title
    - Artist
    - Capo
    - Chart
  - entity: personal-transpose
    effect: reads
    facts:
    - Semitones
  contexts:
    web:
      place: web::bands::concert-mode
- text: The User taps through the pages
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::concert-mode
- text: Past the last page of a song, the Product moves on to the next song of the setlist
  kind: product
  actor: user
  entities:
  - entity: setlist
    effect: reads
    facts:
    - Songs
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::concert-mode
references:
- kind: code
  role: implementation
  target: src/components/ConcertModeView.tsx
---

# Play a setlist

## Trigger

The band is on stage.

## Outcome

The member plays the whole set in order, one song at a time, with the screen kept awake.

## Edge cases

- Text size, autoscroll or pages, and the silent BPM pulse are remembered on each device.
- Stopping takes two presses so a stray tap cannot end the show.
