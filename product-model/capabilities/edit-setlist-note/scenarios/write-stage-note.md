---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the note on a setlist song and writes it
  kind: actor
  actor: user
  entities:
  - entity: setlist
    effect: reads
    facts:
    - Stage notes
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::setlist
- text: The Product saves the trimmed note for that song on this setlist
  kind: product
  actor: user
  entities:
  - entity: setlist
    effect: changes
    facts:
    - Stage notes
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::setlist
references:
- kind: code
  role: implementation
  target: src/context/BandsContext.tsx#updateSongNoteInBandSetlist
---

# Write a note for the stage

## Trigger

The band needs a reminder for one song, such as "Open acoustic, no drums".

## Outcome

The note shows under the song, on the printed sheet and at the top of the song in concert mode.

## Edge cases

- Saving an empty note clears it.
