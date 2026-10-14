---
kind: primary
routes:
  web: Web
steps:
- text: The User writes a note about the take and keeps it pinned to the current moment
  kind: actor
  actor: user
  entities:
  - entity: recording
    effect: reads
    facts:
    - Name
  contexts:
    web:
      place: web::bands::song
- text: The Product adds the comment to the take under the User's name
  kind: product
  actor: user
  entities:
  - entity: recording-comment
    effect: creates
    facts:
    - Text
    - Moment
    - Author
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/recordingComments.ts
---

# Comment at a moment in the take

## Trigger

A member hears something to fix, such as the turnaround at 1:12.

## Outcome

The comment shows its moment, which jumps the player there.

## Edge cases

- Unticking the moment makes it a general comment on the take.
