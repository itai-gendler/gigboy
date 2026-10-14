---
kind: validation
routes:
  feed: Calendar subscription
steps:
- text: The Calendar app fetches the calendar link
  kind: actor
  actor: calendar-app
  entities:
  - entity: calendar-link
    effect: reads
    facts:
    - Link
  contexts:
    feed:
      place: calendar-subscription
- text: The link was turned off, or its member has left or been removed from the band
  kind: condition
  entities:
  - entity: calendar-link
    effect: reads
    facts: []
  - entity: membership
    effect: reads
    facts: []
  - entity: band
    effect: reads
    facts: []
  contexts:
    feed:
      place: calendar-subscription
- text: The Product answers that there is nothing there
  kind: product
  actor: calendar-app
  entities: []
  contexts:
    feed:
      place: calendar-subscription
references:
- kind: code
  role: implementation
  target: server/routes/publicCalendar.ts
- kind: code
  role: implementation
  target: server/routes/gigs.calendar.test.ts
---

# Link turned off or member gone

## Trigger

A calendar app keeps polling an old or orphaned link.

## Outcome

The calendar app receives no gigs.
