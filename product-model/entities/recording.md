---
domain: tools
relations:
- entity: recording-comment
  verb: has
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#songRecordings
- kind: code
  role: implementation
  target: server/routes/songRecordings.ts
---

# Recording

A take recorded in the browser or uploaded to a song, for the band to listen back to.

## Information kept

- **Name** — the name of the take
- **Audio** — the sound itself
- **Length** — how long the take is
- **Waveform** — the waveform drawn for the take
- **Recorded by** — the member who added it
- **Recorded** — when it was added
