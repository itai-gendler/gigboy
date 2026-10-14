---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The User enters a name with the + next to Setlists
  kind: actor
  actor: user
  capability: create-setlist
  entities:
  - entity: setlist
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands
- text: The Product creates the empty setlist and opens it
  kind: product
  actor: user
  capability: create-setlist
  entities:
  - entity: setlist
    effect: creates
    to: Active
    facts:
    - Name
    - Songs
    - Stage notes
  contexts:
    web:
      place: web::bands::setlist
- text: The User opens Add songs and picks songs from the library
  kind: actor
  actor: user
  capability: add-songs-to-setlist
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
    - Artist
  contexts:
    web:
      place: web::bands::setlist
- text: The Product appends the picked songs to the setlist
  kind: product
  actor: user
  capability: add-songs-to-setlist
  entities:
  - entity: setlist
    effect: changes
    facts:
    - Songs
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::setlist
---

# Create a setlist and add songs

## Trigger

An editor prepares the set for an upcoming gig.

## Outcome

The setlist exists with its songs, and its running time shows under its name.
