---
appliesTo:
- type: capability
  id: view-shared-press-kit
- type: capability-scenario
  id: pick-tour-dates
references:
- kind: code
  role: implementation
  target: server/routes/publicPressKits.ts
---

# A shared press kit lists only confirmed, upcoming gigs picked for it

Of the gigs picked on a kit, the shared page lists only those that are confirmed and still ahead, with their title, date, venue, address and tour.
