---
entities:
- entity: song
  shows:
  - Title
- entity: songlist
  shows:
  - Name
- entity: setlist
  shows:
  - Name
- entity: gig
  shows:
  - Title
- entity: tour
  shows:
  - Name
- entity: press-kit
  shows:
  - Name
- entity: press-kit-image
  shows:
  - Title
- entity: technical-rider
  shows:
  - Name
- entity: attachment
  shows:
  - Name
entryPoints:
- web: /bands/:id/trash
references:
- kind: code
  role: implementation
  target: src/components/TrashView.tsx
---

# Trash

The band's deleted songs, songlists, setlists, gigs, tours, press kits, press kit images, technical riders and attachments, each restorable until 30 days have passed.
