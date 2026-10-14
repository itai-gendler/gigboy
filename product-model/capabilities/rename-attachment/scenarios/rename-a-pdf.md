---
kind: primary
routes:
  web: Web
steps:
- text: The User renames their attachment
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
- text: The Product saves the new name
  kind: product
  actor: user
  entities:
  - entity: attachment
    effect: changes
    facts:
    - Name
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/bandAttachments.ts
---

# Rename an attachment

## Trigger

A file name is unclear.

## Outcome

The attachment shows the new name.
