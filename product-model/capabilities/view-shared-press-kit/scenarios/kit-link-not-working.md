---
kind: validation
routes:
  web: Web
steps:
- text: The Visitor opens a public link
  kind: actor
  actor: visitor
  entities: []
  contexts:
    web:
      place: web::public::shared-press-kit
- text: The link was disabled, or its press kit is in the trash
  kind: condition
  entities:
  - entity: press-kit-link
    effect: reads
    facts: []
  - entity: press-kit
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::shared-press-kit
- text: The Product shows that the press kit is not available
  kind: product
  actor: visitor
  entities:
  - entity: press-kit
    effect: reads
    facts: []
  contexts:
    web:
      place: web::public::shared-press-kit
references:
- kind: code
  role: implementation
  target: server/routes/publicPressKits.ts
---

# Link disabled or kit gone

## Trigger

Someone opens an old press kit link.

## Outcome

Nothing of the kit is shown.
