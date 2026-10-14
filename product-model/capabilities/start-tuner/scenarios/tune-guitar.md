---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Start tuner, allows the microphone and plays a string
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::song
- text: The Product shows the note heard and how far it is from pitch
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: src/components/VisualTuner.tsx
---

# Tune a string

## Trigger

An instrument is out of tune at rehearsal.

## Outcome

The member tunes without a separate tuner.

## Edge cases

- On iPhone and iPad the microphone needs the server to be reached over HTTPS.
