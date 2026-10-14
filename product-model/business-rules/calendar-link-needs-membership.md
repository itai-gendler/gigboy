---
appliesTo:
- type: capability
  id: fetch-gig-calendar
- type: capability
  id: leave-band
references:
- kind: code
  role: implementation
  target: server/routes/publicCalendar.ts
---

# A calendar link works only while its member is in the band

A member who leaves or is removed from the band stops receiving its gigs, even if they still have the link.
