---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the recorder on the song, records and names the take
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
- text: The Product saves the take on the song with its length, waveform and who recorded it
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
  target: src/components/SongRecorder.tsx
- kind: code
  role: implementation
  target: server/routes/songRecordings.ts
---

# Record a take

## Trigger

The band rehearses and wants to listen back.

## Outcome

Every bandmate can play the take from the song.

## Edge cases

- A take without a name is called Untitled.
- On iPhone and iPad recording needs the server to be reached over HTTPS.
