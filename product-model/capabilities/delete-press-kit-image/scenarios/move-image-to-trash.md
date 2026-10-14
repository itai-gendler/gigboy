---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete image in the library and confirms
  kind: actor
  actor: user
  entities:
  - entity: press-kit-image
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::bands::press-kit
- text: The Product moves the image to the trash
  kind: product
  actor: user
  entities:
  - entity: press-kit-image
    effect: changes
    from: Active
    to: In trash
    facts: []
  contexts:
    web:
      place: web::bands::press-kit
references:
- kind: code
  role: implementation
  target: server/routes/bandPressKitImages.ts
- kind: code
  role: implementation
  target: server/lib/trash.ts#restoreTrashRow
---

# Move an image to trash

## Trigger

A photo should no longer be offered.

## Outcome

The image waits in the trash for 30 days.

## Edge cases

- Restoring the image puts it back in the kits that had picked it.
