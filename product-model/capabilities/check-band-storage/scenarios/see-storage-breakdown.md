---
kind: primary
routes:
  web: Web
steps:
- text: The User clicks the storage bar under the band name
  kind: actor
  actor: user
  entities:
  - entity: band
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands
- text: The Product shows the storage used by recordings, images and attachments against the storage limit
  kind: product
  actor: user
  entities:
  - entity: recording
    effect: reads
    facts:
    - Audio
  - entity: attachment
    effect: reads
    facts:
    - File
  - entity: press-kit-image
    effect: reads
    facts:
    - Picture
  - entity: band-logo
    effect: reads
    facts:
    - Picture
  - entity: account
    effect: reads
    facts:
    - Storage limit
  contexts:
    web:
      place: web::bands
references:
- kind: code
  role: implementation
  target: server/routes/storageUsage.ts
---

# See the storage breakdown

## Trigger

A member wonders how much room is left.

## Outcome

The member sees what takes up space and how close the band is to the limit.
