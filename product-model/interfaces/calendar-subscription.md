---
type: api
actors:
- calendar-app
entryPoints:
- api: /api/public/calendar/:token.ics
references:
- kind: code
  role: implementation
  target: server/routes/publicCalendar.ts
- kind: code
  role: implementation
  target: server/lib/ics.ts
---

# Calendar subscription

The private iCalendar feed behind each member's calendar link, which calendar
apps poll to keep a band's gigs up to date.
