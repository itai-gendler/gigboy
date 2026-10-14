---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the calendar subscription panel on All gigs and chooses Create my calendar link
  kind: actor
  actor: user
  entities:
  - entity: gig
    effect: reads
    facts: []
  - entity: calendar-link
    effect: reads
    facts: []
  contexts:
    web:
      place: web::bands::gigs
- text: The Product creates the private link, or returns the one the User already has
  kind: product
  actor: user
  entities:
  - entity: calendar-link
    effect: creates
    to: Active
    facts:
    - Link
  contexts:
    web:
      place: web::bands::gigs
- text: The User copies the link or chooses Add to calendar
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
references:
- kind: code
  role: implementation
  target: server/routes/bandCalendarFeed.ts
---

# Create my calendar link

## Trigger

A member wants the band's gigs in Google, Apple or Outlook calendar.

## Outcome

The member's calendar app subscribes to the link and shows the band's gigs with their schedule and contact.

## Edge cases

- Any member can create one, whatever their role.
- The panel offers the link only on All gigs, not on a single tour.
