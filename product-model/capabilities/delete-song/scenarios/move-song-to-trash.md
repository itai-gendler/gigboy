---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Delete on a song and confirms
  kind: actor
  actor: user
  entities:
  - entity: song
    effect: reads
    facts:
    - Title
  contexts:
    web:
      place: web::bands::song
- text: The Product moves the song to the trash and deletes its recordings and attachments for good
  kind: product
  actor: user
  entities:
  - entity: song
    effect: changes
    from: Active
    to: In trash
    facts: []
  - entity: recording
    effect: reads
    facts: []
  - entity: attachment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song
- text: The Product returns the User to the library
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::library
references:
- kind: code
  role: implementation
  target: server/routes/bandSongs.ts
- kind: code
  role: implementation
  target: server/lib/songFiles.ts
---

# Move a song to trash

## Trigger

A song is no longer wanted.

## Outcome

The song is gone from the library and from every setlist and songlist view, and waits in the trash for 30 days.

## Edge cases

- A song can also be deleted from its row in the library.
