---
appliesTo:
- type: capability
  id: create-calendar-link
- type: capability
  id: create-new-calendar-link
references:
- kind: code
  role: implementation
  target: server/routes/bandCalendarFeed.ts
- kind: code
  role: implementation
  target: server/db/schema.ts#calendarFeeds
---

# A member has at most one working calendar link per band

Creating a link when one already works returns that link; a new link replaces the old one.
