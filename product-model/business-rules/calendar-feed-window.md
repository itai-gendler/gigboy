---
appliesTo:
- type: capability
  id: fetch-gig-calendar
  contexts:
  - place: calendar-subscription
references:
- kind: code
  role: implementation
  target: server/routes/publicCalendar.ts
- kind: code
  role: implementation
  target: server/lib/ics.ts
---

# Calendars receive gigs from the past year onward

The calendar subscription carries every upcoming gig and the gigs of the last 365 days; a gig without an end time lasts two hours there.
