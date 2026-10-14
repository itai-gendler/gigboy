---
appliesTo:
- type: capability-scenario
  id: pick-tour-dates
- type: capability
  id: download-press-kit
references:
- kind: code
  role: implementation
  target: server/routes/bandPressKits.ts
---

# A press kit lists only its own band's gigs

Gigs picked on a press kit must belong to the kit's band.
