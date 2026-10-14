---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Empty trash and confirms
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::trash
- text: The Product deletes every trashed song, songlist, setlist, gig, tour, press kit, press kit image and technical rider for good
  kind: product
  actor: user
  entities:
  - entity: song
    effect: removes
    from: In trash
  - entity: songlist
    effect: removes
    from: In trash
  - entity: setlist
    effect: removes
    from: In trash
  - entity: gig
    effect: removes
    from: In trash
  - entity: tour
    effect: removes
    from: In trash
  - entity: press-kit
    effect: removes
    from: In trash
  - entity: press-kit-image
    effect: removes
    from: In trash
  - entity: technical-rider
    effect: removes
    from: In trash
  contexts:
    web:
      place: web::bands::trash
- text: The Product deletes every trashed attachment for good
  kind: product
  actor: user
  entities:
  - entity: attachment
    effect: removes
    from: In trash
  contexts:
    web:
      place: web::bands::trash
references:
- kind: code
  role: implementation
  target: server/routes/bandTrash.ts
---

# Empty the trash

## Trigger

The owner clears the trash.

## Outcome

The trash is empty and nothing in it can be restored.
