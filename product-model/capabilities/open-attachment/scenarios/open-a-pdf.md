---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Open on an attachment
  kind: actor
  actor: user
  entities:
  - entity: attachment
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::song
- text: The Product shows the PDF
  kind: product
  actor: user
  entities:
  - entity: attachment
    effect: reads
    facts:
    - File
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/bandAttachments.ts
---

# Open a PDF

## Trigger

A member needs the sheet music.

## Outcome

The PDF is open to read or save.
