---
domain: tours
references:
- kind: code
  role: implementation
  target: server/db/schema.ts#calendarFeeds
- kind: code
  role: implementation
  target: server/routes/bandCalendarFeed.ts
---

# Calendar link

A member's private link that keeps their calendar app up to date with one band's gigs.

## Information kept

- **Link** — the private address a calendar app subscribes to

## States

### Active

The link works while its member is in the band.

### Turned off

The link no longer works.
