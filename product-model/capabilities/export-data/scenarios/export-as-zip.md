---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Export as ZIP on their profile
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::profile
- text: The Product packs every band's songs, songlists, setlists, recordings, press kits, riders, gigs and tours into one ZIP
  kind: product
  actor: user
  entities:
  - entity: band
    effect: reads
    facts:
    - Name
  - entity: song
    effect: reads
    facts:
    - Title
    - Artist
    - Author
    - Key
    - Capo
    - Tempo
    - Time signature
    - Chart
  - entity: songlist
    effect: reads
    facts:
    - Name
    - Songs
  - entity: setlist
    effect: reads
    facts:
    - Name
    - Songs
    - Stage notes
  - entity: recording
    effect: reads
    facts:
    - Name
    - Audio
  - entity: press-kit
    effect: reads
    facts:
    - Name
    - Text
    - Images
    - Tour dates
  - entity: press-kit-image
    effect: reads
    facts:
    - Title
    - Picture
  - entity: technical-rider
    effect: reads
    facts:
    - Name
    - Stage plot
    - Input list
    - Logistics
    - Hospitality
  - entity: gig
    effect: reads
    facts:
    - Title
    - On stage
    - Venue
    - Tour
    - Setlist
    - Technical rider
    - Press kit
  - entity: tour
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::profile
references:
- kind: code
  role: implementation
  target: src/lib/songbookExport.ts
---

# Export as ZIP

## Trigger

A user wants their data outside Gigboy.

## Outcome

The user has a ZIP whose songs open in any ChordPro app.
