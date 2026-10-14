---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Disable public link and confirms
  kind: actor
  actor: user
  entities:
  - entity: press-kit-link
    effect: reads
    facts:
    - Link
  contexts:
    web:
      place: web::bands::press-kit
- text: The Product disables the link
  kind: product
  actor: user
  entities:
  - entity: press-kit-link
    effect: changes
    from: Active
    to: Disabled
    facts: []
  contexts:
    web:
      place: web::bands::press-kit
references:
- kind: code
  role: implementation
  target: server/routes/bandPressKitShares.ts
---

# Disable the public link

## Trigger

The kit should no longer be public.

## Outcome

Anyone with the old link loses access; sharing again creates a new link.
