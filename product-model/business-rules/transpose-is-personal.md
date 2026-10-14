---
appliesTo:
- type: capability
  id: transpose-song
- type: capability
  id: start-concert-mode
references:
- kind: code
  role: implementation
  target: server/routes/songMemberPrefs.ts
- kind: code
  role: implementation
  target: src/components/ConcertModeView.tsx
---

# Each member's transpose is their own

A member's transpose for a song is kept for that member only and is where the song opens for them, on the song page and in concert mode; it never changes the chart for bandmates.
