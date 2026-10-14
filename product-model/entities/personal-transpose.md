---
domain: library
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#songMemberPrefs
- kind: code
  role: implementation
  target: server/routes/songMemberPrefs.ts
---

# Personal transpose

The transpose one member reads one song in. Each bandmate keeps their own, so the horn player can read in E-flat without touching anyone else's chart.

## Information kept

- **Semitones** — the shift, from 11 down to 11 up
