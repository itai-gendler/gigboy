---
domain: tools
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#bandChordVoicings
- kind: code
  role: implementation
  target: server/routes/bandChordVoicings.ts
---

# Chord voicing

The fingering a band actually plays for a chord on guitar or ukulele, used instead of the built-in diagram.

## Information kept

- **Instrument** — Guitar or Ukulele
- **Chord** — the chord name
- **Fingering** — the fret for each string, muted or open where marked
