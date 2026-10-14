---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses New link in the calendar subscription panel
  kind: actor
  actor: user
  entities:
  - entity: calendar-link
    as: old
    effect: reads
    facts:
    - Link
  contexts:
    web:
      place: web::bands::gigs
- text: The Product turns the old link off and creates a new one
  kind: product
  actor: user
  entities:
  - entity: calendar-link
    as: old
    effect: changes
    from: Active
    to: Turned off
    facts: []
  - entity: calendar-link
    as: new
    effect: creates
    to: Active
    facts:
    - Link
  contexts:
    web:
      place: web::bands::gigs
references:
- kind: code
  role: implementation
  target: server/routes/bandCalendarFeed.ts
---

# Replace a leaked link

## Trigger

The member's link was shared or leaked.

## Outcome

The old address no longer works; calendar apps must subscribe to the new one.
