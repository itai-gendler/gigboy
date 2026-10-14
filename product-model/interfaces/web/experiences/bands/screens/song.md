---
entities:
- entity: song
  shows:
  - Title
  - Artist
  - Author
  - Chart
  - Key
  - Capo
  - Tempo
  - Time signature
  - Duration
  - Playback link
- entity: personal-transpose
  shows:
  - Semitones
- entity: songlist
  shows:
  - Name
- entity: setlist
  shows:
  - Name
- entity: recording
  shows:
  - Name
  - Audio
  - Length
  - Recorded by
  - Recorded
  collects:
  - Name
  - Audio
- entity: recording-comment
  shows:
  - Text
  - Moment
  - Author
  collects:
  - Text
  - Moment
- entity: attachment
  shows:
  - Name
  - File
  - Uploaded by
  collects:
  - Name
  - File
- entity: song-note
  shows:
  - Drawing
  - Typed notes
  - Author
  collects:
  - Drawing
  - Typed notes
- entity: song-version
  shows:
  - Saved
  - Saved by
  - Changes
  - Song details
- entity: chord-voicing
  shows:
  - Instrument
  - Chord
  - Fingering
  collects:
  - Fingering
entryPoints:
- web: /songs/:id
references:
- kind: code
  role: implementation
  target: src/pages/SongPage.tsx
- kind: code
  role: implementation
  target: src/components/SongView.tsx
---

# Song

One song: its chart and details, read with your own transpose.
