---
appliesTo:
- type: capability
  id: edit-chord-voicing
- type: capability
  id: start-concert-mode
references:
- kind: code
  role: implementation
  target: src/hooks/useBandChordVoicings.ts
---

# A band's chord voicing replaces the built-in diagram everywhere

Wherever members of the band tap that chord on that instrument — song pages and concert mode — they see the band's fingering; voicings exist for guitar and ukulele only.
