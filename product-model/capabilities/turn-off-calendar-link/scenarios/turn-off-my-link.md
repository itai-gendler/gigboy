---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Turn off in the calendar subscription panel
  kind: actor
  actor: user
  entities:
  - entity: calendar-link
    effect: reads
    facts:
    - Link
  contexts:
    web:
      place: web::bands::gigs
- text: The Product turns the link off
  kind: product
  actor: user
  entities:
  - entity: calendar-link
    effect: changes
    from: Active
    to: Turned off
    facts: []
  contexts:
    web:
      place: web::bands::gigs
references:
- kind: code
  role: implementation
  target: server/routes/bandCalendarFeed.ts
---

# Turn off my link

## Trigger

A member no longer wants the subscription.

## Outcome

The link stops working; the member can create a new one later.
