---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The User enters a name with the + next to Songlists
  kind: actor
  actor: user
  capability: create-songlist
  entities:
  - entity: songlist
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands
- text: The Product creates the empty songlist and opens it
  kind: product
  actor: user
  capability: create-songlist
  entities:
  - entity: songlist
    effect: creates
    to: Active
    facts:
    - Name
    - Songs
  contexts:
    web:
      place: web::bands::songlist
- text: The User picks a library song from the songlist
  kind: actor
  actor: user
  capability: add-song-to-songlist
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
    - Artist
  - entity: songlist
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::songlist
- text: The Product appends the song to the songlist
  kind: product
  actor: user
  capability: add-song-to-songlist
  entities:
  - entity: songlist
    effect: changes
    facts:
    - Songs
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::songlist
---

# Create a songlist and add songs

## Trigger

An editor gathers songs under a theme, such as "Songs we're learning".

## Outcome

The songlist exists with its songs.
