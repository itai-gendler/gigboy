---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Upload audio file on the recorder and picks a file
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::bands::song
- text: The Product saves the file as a take on the song
  kind: product
  actor: user
  entities:
  - entity: recording
    effect: creates
    facts:
    - Name
    - Audio
    - Length
    - Waveform
    - Recorded by
    - Recorded
  - entity: song
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::song
references:
- kind: code
  role: implementation
  target: server/routes/songRecordings.ts
---

# Upload an audio file

## Trigger

A member has a take recorded elsewhere.

## Outcome

The take is on the song like a recorded one.

## Edge cases

- Audio must be WebM, Ogg, MP3, M4A or WAV of at most 50 MB.
