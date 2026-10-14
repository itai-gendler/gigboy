---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The User enters a name with the + next to the band switcher
  kind: actor
  actor: user
  capability: create-band
  entities:
  - entity: band
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands
- text: The Product creates the band owned by the User and opens its empty library
  kind: product
  actor: user
  capability: create-band
  entities:
  - entity: band
    effect: creates
    facts:
    - Name
  - entity: membership
    effect: creates
    facts:
    - Role
    - Joined
    with: band
  contexts:
    web:
      place: web::bands::library
- text: The User presses the add button in the library and writes the song
  kind: actor
  actor: user
  capability: add-song
  entities:
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song-editor
- text: The Product saves the song to the library
  kind: product
  actor: user
  capability: add-song
  entities:
  - entity: song
    effect: creates
    to: Active
    facts:
    - Title
    - Artist
    - Author
    - Language
    - Other languages
    - Tags
    - Chart
    - Key
    - Tempo
    - Time signature
    - Date
    - Duration
    - Playback link
  contexts:
    web:
      place: web::bands::song-editor
---

# Create a band and add its first song

## Trigger

A musician brings their band to Gigboy.

## Outcome

The band exists with its first song.
