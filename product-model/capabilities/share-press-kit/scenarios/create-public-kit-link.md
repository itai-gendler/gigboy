---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Share on the press kit
  kind: actor
  actor: user
  entities:
  - entity: press-kit
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::press-kit
- text: The Product creates the public link, or returns the one the kit already has
  kind: product
  actor: user
  entities:
  - entity: press-kit-link
    effect: creates
    to: Active
    facts:
    - Link
  contexts:
    web:
      place: web::bands::press-kit
- text: The Product copies the link for the User to paste
  kind: product
  actor: user
  entities:
  - entity: press-kit-link
    effect: reads
    facts:
    - Link
  contexts:
    web:
      place: web::bands::press-kit
references:
- kind: code
  role: implementation
  target: server/routes/bandPressKitShares.ts
- kind: code
  role: implementation
  target: server/lib/pressKitOg.ts
---

# Create and copy the public link

## Trigger

A promoter asks for the band's press kit.

## Outcome

Anyone the link is sent to can read the kit without an account, and it previews with the band name and bio when pasted into an email or chat.
