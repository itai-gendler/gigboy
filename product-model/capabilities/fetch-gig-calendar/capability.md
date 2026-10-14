---
availability:
- place: calendar-subscription
domain: tours
references:
- kind: code
  role: implementation
  target: server/routes/publicCalendar.ts
- kind: code
  role: implementation
  target: server/lib/ics.ts
---

# Fetch the gig calendar

A calendar app fetches a member's calendar link and receives the band's gigs as calendar events.
