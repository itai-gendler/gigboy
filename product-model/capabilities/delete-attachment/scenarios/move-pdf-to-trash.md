---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete on their attachment and confirms
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
- text: The Product moves the attachment to the trash
  kind: product
  actor: user
  entities:
  - entity: attachment
    effect: changes
    from: Active
    to: In trash
    facts: []
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/bandAttachments.ts
---

# Move an attachment to trash

## Trigger

A PDF is outdated.

## Outcome

The attachment waits in the trash for 30 days.
