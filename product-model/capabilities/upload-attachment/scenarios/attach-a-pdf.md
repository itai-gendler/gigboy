---
kind: primary
routes:
  web: Web
steps:
- text: The User picks a PDF in the song's attachments
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts: []
  - entity: attachment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song
- text: The Product stores the PDF on the song under the User's name
  kind: product
  actor: user
  entities:
  - entity: attachment
    effect: creates
    to: Active
    facts:
    - Name
    - File
    - Uploaded by
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/bandAttachments.ts
---

# Attach a PDF

## Trigger

The band has sheet music or a horn chart for the song.

## Outcome

Every member can open the PDF from the song.
