---
kind: alternative
routes:
  web: Web
steps:
- text: The User presses the key arrows on a song they already transposed
  kind: actor
  actor: user
  entities:
  - entity: personal-transpose
    effect: reads
    facts:
    - Semitones
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song
- text: The Product saves the new shift for the User
  kind: product
  actor: user
  entities:
  - entity: personal-transpose
    effect: changes
    facts:
    - Semitones
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/songMemberPrefs.ts
---

# Change a kept transpose

## Trigger

A member settles on yet another key.

## Outcome

The new key is what this member sees from now on.
