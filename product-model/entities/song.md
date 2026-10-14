---
domain: library
relations:
- entity: personal-transpose
  verb: has
  cardinality: one-to-many
- entity: recording
  verb: has
  cardinality: one-to-many
- entity: attachment
  verb: has
  cardinality: one-to-many
- entity: song-note
  verb: has
  cardinality: one-to-many
- entity: song-version
  verb: has
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#songs
- kind: code
  role: implementation
  target: server/routes/bandSongs.ts
---

# Song

A song in the band's library: its details and its chart in ChordPro.

## Information kept

- **Title** — required
- **Artist** — who performs it
- **Author** — the songwriter
- **Language** — the main language; English unless set
- **Other languages** — further languages the lyrics use
- **Tags** — free labels for finding songs
- **Chart** — lyrics and chords in ChordPro; required
- **Key** — the musical key
- **Capo** — the capo fret, shared by the whole band
- **Tempo** — beats per minute
- **Time signature** — the meter
- **Date** — a free date for the song itself, such as when it was written or learned
- **Duration** — the play length, used for setlist running times
- **Playback link** — a YouTube or Spotify link that adds a small player to the song

## States

### Active

In use in the band.

### In trash

Moved to the band trash; restorable for 30 days, then deleted for good.
