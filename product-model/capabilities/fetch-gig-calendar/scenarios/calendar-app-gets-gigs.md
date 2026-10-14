---
kind: primary
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
- text: The Product checks the link is active and its member is still in the band
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
- text: The Product returns the band's gigs from the past year onward, each with its time, venue, status and a description of schedule, contact, tour, setlist, rider, press kit and notes
  kind: product
  actor: calendar-app
  entities:
  - entity: band
    effect: reads
    facts:
    - Name
  - entity: gig
    effect: reads
    facts:
    - Title
    - On stage
    - Ends
    - Get in
    - Sound check
    - Time zone
    - Venue
    - Address
    - Contact name
    - Contact phone
    - Contact email
    - Notes
    - Status
    - Tour
    - Setlist
    - Technical rider
    - Press kit
  - entity: setlist
    effect: reads
    facts: []
  - entity: tour
    effect: reads
    facts: []
  - entity: press-kit
    effect: reads
    facts: []
  contexts:
    feed:
      place: calendar-subscription
references:
- kind: code
  role: implementation
  target: server/routes/publicCalendar.ts
- kind: code
  role: implementation
  target: server/lib/ics.ts
---

# Receive the band's gigs

## Trigger

The member's calendar app polls the link on its own schedule.

## Outcome

The calendar shows a calendar named after the band, with every gig of the past year and all upcoming ones; edited gigs update and cancelled gigs show as cancelled.

## Edge cases

- A gig with no end time lasts two hours in the calendar.
- Times in the description are shown in the time zone the gig was entered in.
