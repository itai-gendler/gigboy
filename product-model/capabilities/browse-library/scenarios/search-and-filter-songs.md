---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the library
  kind: actor
  actor: user
  entities:
  - entity: band
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::library
- text: The Product lists every active song of the library
  kind: product
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
    - Artist
    - Language
    - Key
    - Tempo
    - Date
    - Duration
    - Tags
  contexts:
    web:
      place: web::bands::library
- text: The User types a search and sets key and tempo filters
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::library
- text: The Product keeps the songs whose title, artist, tags or language match and that fit the filters
  kind: product
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
    - Artist
    - Tags
    - Language
    - Key
    - Tempo
  contexts:
    web:
      place: web::bands::library
references:
- kind: code
  role: implementation
  target: src/components/SongList.tsx
- kind: code
  role: implementation
  target: src/components/SongFilterPanel.tsx
---

# Search, sort and filter the library

## Trigger

A member looks for a song.

## Outcome

The library shows only the matching songs, in the chosen order: by name, artist, language or date added.

## Edge cases

- Tempo filters group songs as slow, mid, upbeat or fast.
- Active filters show as chips in the bar while the filter panel is closed.
